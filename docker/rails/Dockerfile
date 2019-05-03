FROM ruby:2.6.3
ENV LANG C.UTF-8
# for postgreSQL
#RUN apt-get update -qq && apt-get install -y build-essential libpq-dev  nodejs
# for mariaDB
RUN apt-get update -qq \
    && apt-get install -y build-essential nodejs mysql-client \
    && rm -rf /var/lib/apt/lists/*

RUN gem install bundler

WORKDIR /tmp
ADD Gemfile Gemfile
ADD Gemfile.lock Gemfile.lock
RUN bundle install

ENV APP_HOME /myapp
RUN mkdir -p $APP_HOME
WORKDIR $APP_HOME
ADD . $APP_HOME
