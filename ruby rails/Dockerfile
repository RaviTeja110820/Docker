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

# Set the working directory to /app
WORKDIR /app

# Copy the zip file to the container
ADD myapp.zip /app/

RUN unzip myapp.zip && \
    rm myapp.zip && \
    mv * myapp

# Set the working directory to /app/myapp
WORKDIR /app/myapp

# Install dependencies
# yarn install will install JavaScript dependencies defined in a package.json file.
# ENV BUNDLE_PATH /gems
# RUN yarn install
RUN bundle install

# Expose port 3000
EXPOSE 3000

# Entry point 
# ENTRYPOINT [ "bin/rails" ]

# Start the Rails server
CMD ["rails", "server", "-b", "0.0.0.0"]

# Expose port 3000
# EXPOSE 3000