FROM python:3.6.0-alpine

WORKDIR /app
COPY . /app

RUN apk --no-cache --update add build-base gcc musl-dev && \
    pip install -r requirements.txt && \
    apk del build-base

ENV POST_DATABASE_HOST="post_db" POST_DATABASE="posts"

ENTRYPOINT ["python3", "post_app.py"]
