FROM ruby:2.5-alpine
RUN apk update 
RUN apk add nodejs
# RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
# ENV RAILS_ROOT /var/www/app
# RUN mkdir -p $RAILS_ROOT
# RUN bundle install --jobs 20 --retry 5 --without development test
# RUN apt-get install build-essetial patch ruby-dev zlib1g-dev liblzma-dev
# COPY . /apptest
# WORKDIR /apptest
ADD Gemfile Gemfile
ADD Gemfile.lock Gemfile.lock
RUN apk update && \
    apk add --no-cache \
    tzdata git make \
    build-base bash openssh \
    mysql \
    mysql-client \
    mysql-dev  \
    imagemagick \
    libffi-dev \
    nano \
    ls
RUN gem install bundler:2.1.4
RUN apk add --no-cache build-base
# RUN apk add libmysqlclient-dev
RUN gem install mysql2
RUN gem install ffi
RUN gem install nokogiri
RUN bundle install

ENV RAILS_ROOT ./apptest
COPY . /apptest
RUN mkdir -p $RAILS_ROOT
WORKDIR $RAILS_ROOT

ENV RAILS_ENV='production'
ENV RACK_ENV='production'
ENV PORT 3000
# ENTRYPOINT ./entrypoint.sh

COPY Gemfile Gemfile
COPY Gemfile.lock Gemfile.lock

COPY . .
# RUN bundle exec rake assets:precompile
RUN SECRET_KEY_BASE=1 RAILS_ENV=production bin/rails assets:precompile

EXPOSE 3000
CMD ["bundle", "exec", "puma", "-C", "config/puma.rb"]
