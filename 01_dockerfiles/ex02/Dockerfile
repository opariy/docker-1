FROM ruby

RUN apt-get -y update 
RUN apt-get -y upgrade
RUN apt-get install -y nodejs
RUN gem update
RUN gem install bundler
RUN gem install rails

ONBUILD WORKDIR /opt/app
ONBUILD COPY . /opt/app
ONBUILD RUN bundle install && rails db:migrate && rails db:seed

# docker run -p 5000:80 -t