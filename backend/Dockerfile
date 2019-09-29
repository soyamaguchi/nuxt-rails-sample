FROM ruby:2.6.4

# 必要なライブラリをインストール
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev postgresql-client nodejs

ENV APP_DIR /app/backend
# Rails App
RUN mkdir -p /app/backend
WORKDIR $APP_DIR
COPY Gemfile $APP_DIR/Gemfile
COPY Gemfile.lock $APP_DIR/Gemfile.lock
RUN bundle install
COPY . $APP_DIR
