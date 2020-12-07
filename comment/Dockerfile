FROM alpine:3.9

RUN apk add --no-cache ruby-full ruby-dev \
    gcc musl-dev make \
    && gem install bundler:1.17.2 --no-ri --no-rdoc

ENV APP_HOME /app
RUN mkdir $APP_HOME

WORKDIR $APP_HOME
COPY . $APP_HOME
# COPY Gemfile* $APP_HOME/

RUN bundle install

ENV COMMENT_DATABASE_HOST="comment_db" COMMENT_DATABASE="comments"

CMD ["puma"]
