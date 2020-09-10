FROM ubuntu:18.04

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update -qq 
RUN apt-get install -qqy --no-install-recommends apt-utils
RUN apt-get install -y build-essential wget

RUN wget -qO - https://packages.microsoft.com/keys/microsoft.asc | tee /etc/apt/trusted.gpg.d/microsoft.asc

RUN wget -qO - https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/microsoft.list

RUN apt-get install -y apt-transport-https
RUN apt-get update
RUN apt-get install -y dotnet-runtime-2.1

ARG PKIE_VERSION='pkie-1.18.0.tar.gz'
ARG PKIE_SHA512='a3b37c97336d90f6519b9252157fa981b80454d35b75c668f006c220dbeb0aaa7cf8b68463f902955a2dced4f3158374247e10a1eca5d3178650b0b7097d1b2d'

RUN wget -q https://cdn.lacunasoftware.com/pki-express/linux/${PKIE_VERSION} \
    && echo "${PKIE_SHA512} ${PKIE_VERSION}" | sha512sum -c -
RUN mkdir /usr/share/pkie
RUN tar xzf ${PKIE_VERSION} -C /usr/share/pkie
RUN chmod -R a=r,a+X,u+w /usr/share/pkie

RUN echo '#!/bin/bash' | tee /usr/local/bin/pkie
RUN echo 'dotnet /usr/share/pkie/pkie.dll "$@"' | tee -a /usr/local/bin/pkie
RUN chmod +x /usr/local/bin/pkie

RUN mkdir /var/log/pkie
RUN chmod 777 /var/log/pkie
RUN pkie config --set logDir=/var/log/pkie