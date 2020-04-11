#Docker Build file to create the runtime Matlab 2018a image
from ubuntu:xenial
MAINTAINER tperezdevelopment@gmail.com


RUN apt-get update
RUN apt-get install -y  \
    unzip \
    wget \	
   libgl-dev \
   libglu-dev \
libxrandr-dev --fix-missing \
  g++ \
libxt-dev  
RUN wget -nc --quiet https://ssd.mathworks.com/supportfiles/downloads/R2018a/deployment_files/R2018a/installers/glnxa64/MCR_R2018a_glnxa64_installer.zip
RUN unzip MCR_R2018a_glnxa64_installer.zip -d mcr-install
RUN /mcr-install/install -mode silent -agreeToLicense yes
RUN cd .. && rm -r mcr-install
RUN rm MCR_R2018a_glnxa64_installer.zip
ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/MATLAB/MATLAB_Runtime/v94/runtime/glnxa64:/usr/local/MATLAB/MATLAB_Runtime/v94/bin/glnxa64
ENV LD_PRELOAD=/usr/local/MATLAB/MATLAB_Runtime/v94/sys/os/glnxa64/libstdc++.so.6.0.22

