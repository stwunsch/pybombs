# Base image
FROM centos:7

# Minimal package installation
RUN rpm -iUvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm &&\
    yum -y update &&\
    yum -y install python-pip git

# PyBOMBS setup
WORKDIR /pybombs
RUN pip install PyBOMBS
RUN pybombs -v prefix init /pybombs
RUN pybombs -v recipes add gr-recipes git+https://github.com/gnuradio/gr-recipes.git &&\
    pybombs -v recipes add gr-etcetera git+https://github.com/gnuradio/gr-etcetera.git
