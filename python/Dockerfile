FROM python:3.8-buster

RUN apt-get update

RUN pip install --upgrade pip

RUN mkdir /app

WORKDIR /app

ADD requirements.txt /app/

RUN pip install -r requirements.txt