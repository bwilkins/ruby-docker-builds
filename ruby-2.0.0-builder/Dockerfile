FROM bwilkins/ruby:ruby-2.0.0-p247

RUN bash -c 'apt-get -y install build-essential libpq-dev libxml2-dev libxslt-dev'

RUN gem install bundler
# ADD Gemfile /image-build/
# RUN bash -c "cd /image-build; bundle install --without='test development'"
