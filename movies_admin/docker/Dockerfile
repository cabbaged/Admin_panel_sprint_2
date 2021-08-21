FROM python:3-slim

RUN apt-get update -y \
&& apt install -y gcc

COPY requirements /project/
WORKDIR /project

RUN pip3 install -r production.txt

COPY . /project

CMD uwsgi --ini config/uwsgi.ini
