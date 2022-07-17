FROM python:3.9
ENV PYTHONUNBUFFERED 1

RUN mkdir /web_django
WORKDIR /var/www
COPY . /var/www/barcodes

RUN apt update && apt install -y nano

WORKDIR /var/www/barcodes
RUN pip install --upgrade pip && pip install -r requirements.txt

CMD gunicorn timer_ws.wsgi:application --bind 0.0.0.0:8000