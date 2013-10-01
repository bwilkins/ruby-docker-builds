FROM ubuntu

RUN dpkg-divert --local --rename --add /sbin/initctl
RUN ln -s /bin/true /sbin/initctl
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

RUN apt-get install -y ruby1.9.3 build-essential wget git curl nginx jenkins firefox xvfb

RUN gem update --no-rdoc --no-ri
RUN gem install ohai --no-rdoc --no-ri
RUN /bin/bash -c 'curl -L https://www.opscode.com/chef/install.sh | bash'

RUN groupadd admin

ADD places_runlist.json /tmp/
ADD places_chef_config.rb /tmp/
ADD sudoers /etc/

RUN /bin/bash -c "cd /tmp/; git clone https://github.com/markba/chef-hooroo.git"

RUN chef-solo -c /tmp/places_chef_config.rb
