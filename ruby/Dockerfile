#
# Ruby 2.1.10
# 

# iull base image.
FROM ruby:2.1.10

# install node
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get update
RUN apt-get install -y nodejs

# install some stuff I use
RUN wget http://download.opensuse.org/repositories/shells:fish:release:2/Debian_8.0/Release.key
RUN apt-key add - < Release.key
RUN echo 'deb http://download.opensuse.org/repositories/shells:/fish:/release:/2/Debian_8.0/ /' > /etc/apt/sources.list.d/fish.list
RUN apt-get update
RUN apt-get install -y fish htop

# GEMs
RUN gem install bundler
ADD Gemfile* $APP_HOME/

RUN bundle install

## Create the project directory
ENV APP_HOME /opt/jila
RUN mkdir $APP_HOME
WORKDIR $APP_HOME
