# Use Ruby 2.7.0 as base image
FROM ruby:2.7.0

# Install dependencies
RUN apt-get update -qq && \
    apt-get install -y --no-install-recommends \
    build-essential \
    libpq-dev \
    nodejs \
    default-mysql-client \
    default-libmysqlclient-dev \
    tzdata && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir /app
# Set the working directory to /app
WORKDIR /app
ADD Gemfile /app/Gemfile
ADD Gemfile.lock /app/Gemfile.lock
RUN bundle install
ADD . /app
