FROM martinkaburu/python3.7-alpine

RUN mkdir -p /usr/src/
WORKDIR /usr/src

COPY .. .

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apk update && apk add \
    postgresql-dev \
    gcc \
    python3-dev \
    musl-dev

RUN pip3 install --upgrade pip
COPY requirements.txt .
RUN pip3 install -r requirements.txt

RUN pip3 install gunicorn

VOLUME /my_volume

CMD ["python", "manage.py", 'runserver', '0.0.0.0:8000']