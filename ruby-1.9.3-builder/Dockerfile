FROM bwilkins/ruby:ruby-1.9.3-p448
RUN locale-gen en_AU.UTF-8
RUN update-locale LANG=en_AU.UTF-8
ENV LANG en_AU.UTF-8

RUN bash -c 'apt-get -y install build-essential libpq-dev libxml2-dev libxslt-dev git-core'

RUN gem install bundler
ADD .ssh /root/.ssh
ADD Gemfile /image-build/
RUN bash -c "cd /image-build; bundle install --without='test development assets'"
