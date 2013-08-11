FROM ubuntu

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

RUN bash -c 'yes | apt-get install gdebi-core'
RUN bash -c 'yes | apt-get install libpq5 libxml2 libxslt1.1'
RUN bash -c 'yes | apt-get install build-essential libpq-dev libxml2-dev libxslt-dev'

RUN mkdir /image-build
ADD build/ruby-1.9.3-1.9.3-p448_amd64.deb /image-build/

RUN bash -c "cd /image-build; yes | gdebi ruby-1.9.3-1.9.3-p448_amd64.deb"

RUN gem install bundler

ADD Gemfile /image-build/
RUN bash -c "cd /image-build; bundle install --without='test development'"
