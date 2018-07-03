FROM ruby

ONBUILD COPY ./ruby-task/ /opt/app

RUN apt-get update -y && apt-get upgrade -y 
RUN gem install rails
RUN apt-get install nodejs -y

ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:setup
ONBUILD RUN rake db:seed
