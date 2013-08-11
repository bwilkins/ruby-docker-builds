FROM ubuntu
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN bash -c 'yes | apt-get install gdebi-core'
RUN mkdir /image-build
ADD build/ruby-2.0.0-2.0.0-p247_amd64.deb /image-build/
RUN bash -c "cd /image-build; yes | gdebi ruby-2.0.0-2.0.0-p247_amd64.deb"
