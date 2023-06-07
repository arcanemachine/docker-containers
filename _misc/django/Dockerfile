# syntax=docker/dockerfile:1

FROM python:3.9-slim-bullseye

# set environment variables for python
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# work in /code
WORKDIR /code

# copy requirements.txt to /code
COPY requirements.txt /code/

# install django and copy contents to container
RUN pip install -r requirements.txt
COPY . /code/
