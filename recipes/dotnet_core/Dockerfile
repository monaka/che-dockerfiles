# Copyright (c) 2012-2016 Codenvy, S.A.
# All rights reserved. This program and the accompanying materials
# are made available under the terms of the Eclipse Public License v1.0
# which accompanies this distribution, and is available at
# http://www.eclipse.org/legal/epl-v10.html
# Contributors:
# Abel García Dorta <mercuriete@gmail.com> 
# Roger S <narayanroger@gmail.com>

FROM eclipse/stack-base:ubuntu

MAINTAINER narayanroger@gmail.com

RUN sudo apt-get update && \
    sudo apt-get install apt-transport-https -y && \
    echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" | sudo tee --append /etc/apt/sources.list.d/dotnetdev.list && \
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 417A0893 &&\
    sudo apt-get update && \
    sudo apt-get install dotnet-dev-1.0.1 -y && \
    sudo apt-get clean && \
    sudo apt-get -y autoremove && \
    sudo apt-get -y clean && \
    sudo rm -rf /var/lib/apt/lists/*
    
RUN curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
RUN sudo apt-get install nodejs -y
RUN sudo npm install -g yo bower grunt-cli gulp
RUN sudo npm install -g generator-aspnet

ENV LANG C.UTF-8
EXPOSE 5000
LABEL che:server:5000:ref=dot.net.server che:server:5000:protocol=http
