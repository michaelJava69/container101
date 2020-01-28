FROM ubuntu:latest
MAINTAINER michael.professional@inbox.com

RUN apt-get update	
RUN apt-get install -y nodejs
#RUN apt-get install -y nodejs-legacy
RUN apt-get install -y npm
RUN apt-get clean

COPY ./package.json src/           
# If package.json changes then expesive npm install
# after Copy package.json to src/
RUN cd src  && npm install

COPY . src/		           
# If something added to present context copy context to src

WORKDIR src/		           
# set workspace as src/


# default CMD
CMD ["npm" , "start" ]		   
# Default command

