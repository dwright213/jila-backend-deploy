# base image
FROM ubuntu:14.04
MAINTAINER Dan Wright <muscle.crab.13@gmail.com>

# basics
RUN apt-get update && apt-get install -y curl nginx openssh-server git-core openssh-client vim
RUN apt-get install -y openssl libreadline6 libreadline6-dev curl zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion pkg-config build-essential

# packages specifically required by gems
RUN apt-get install -y libpq-dev nodejs

# Compile ruby, get bundler
RUN cd /tmp/
RUN wget http://ftp.ruby-lang.org/pub/ruby/2.1/ruby-2.1.2.tar.gz
RUN tar -xvzf ruby-2.1.2.tar.gz
WORKDIR ruby-2.1.2/
RUN ./configure --prefix=/usr/local
RUN make
RUN sudo make install


RUN gem install bundler
RUN mkdir /jila-backend/
WORKDIR /jila-backend/

EXPOSE 3000
