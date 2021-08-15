FROM ubuntu:18.04

RUN apt-get update -y \
&& apt install -y python3 python3-pip libpq-dev python-dev

COPY . /project
WORKDIR /project

RUN pip3 install -r requirements/production.txt

CMD python3 manage.py collectstatic --noinput --settings=config.settings.production ; \
python3 manage.py migrate --settings=config.settings.production ; \
uwsgi --ini config/uwsgi.ini
