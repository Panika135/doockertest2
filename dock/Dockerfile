FROM martinkaburu/python3.7-alpine


ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1

WORKDIR /code

COPY . /code/

RUN apk update && apk add \
    postgresql-dev \
    gcc \
    python3-dev \
    musl-dev

RUN pip install --upgrade pip
RUN pip install -r requirements.txt
RUN pip install gunicorn
