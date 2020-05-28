FROM ubuntu:bionic

# Install some packages
RUN apt-get update \
	&& apt-get install -y \
		vim \
		ssh \
		sudo \
		wget \
		software-properties-common \
    make \
    gfortran;\
		rm -rf /var/lib/apt/lists/*

# Create a new user called swash
RUN useradd --user-group --create-home --shell /bin/bash swash ;\
	echo "swash ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# Set Working directory
WORKDIR /home/swash

# Copy local tar with source code
ADD --chown=swash ./swash-6.01.tar ./source

# Install SWASH - serial
RUN cd ./source/swash;\
    make config;\
    make ser;\
    chmod +rx swashrun;\
    mkdir -p ~/data

# Create some Environmental variables
ENV PATH="/home/swash/source/swash:${PATH}"
ENV data="~/data"

# set the default container user to swash
USER swash
