#10.x tested to work as well #6.x tested and fails
FROM node:8-stretch

#Install necessary packages and purge update cache (Just takes up space)
#RUN apt-get update && \
#apt-get install -y nodejs npm git && \
#rm -rf /var/lib/apt/lists/*
#RUN nodejs -v

#requires babel-runtime
#npm install bable-runtime --save

# Install necessary packages and purge update cache
# doing in one step for better docker layer efficiency
RUN apt-get update && \
# general utilities
apt-get install --fix-missing -y git nano wget zip && \
apt-get install --fix-missing -y \
#python 3.5 build tools
python3-pip binutils libproj-dev gdal-bin libpq-dev libncurses5-dev \
libxml2-dev libxslt1-dev python-dev tzdata libsasl2-dev \
default-libmysqlclient-dev && \
#Rails 2.3 build tools
apt-get install --fix-missing -y \
ruby2.3 ruby2.3-dev gem && \
# purge update cache to save space
rm -rf /var/lib/apt/lists/*

RUN pip3 install boto3 awscli
