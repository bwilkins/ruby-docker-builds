FROM ubuntu
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN bash -c 'yes | apt-get install gdebi-core'
RUN mkdir /image-build
ADD build/ruby-1.9.3-1.9.3-p448_amd64.deb /image-build/
RUN bash -c "cd /image-build; yes | gdebi ruby-1.9.3-1.9.3-p448_amd64.deb"
