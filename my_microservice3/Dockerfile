FROM ubuntu:latest
MAINTAINER michael.professional@inbox.com

RUN apt-get update
RUN apt-get install -y curl

RUN curl --silent --location https://deb.nodesource.com/setup_11.x | bash -
RUN apt-get install -y nodejs
RUN apt-get clean

RUN mkdir src/

#COPY ./package.json src/
#RUN cd src  && npm install
#COPY . src/

WORKDIR src/

# default CMD
CMD ["npm" , "start" ]

############################################################
# ONBUILD commands replacing previous three steps
# We now have a template to build chlid containers
# No goto to microservice folder and change Dpcker file to pint at the taggged build for this i.e my-microservice:0.1
############################################################

# copy json package from current to workspace
ONBUILD COPY ./package.json ./

ONBUILD  RUN npm install

# copy rest code from current to workspace
ONBUILD COPY . .

# default CMD
#CMD ["npm" , "start" ]

