# Base image
FROM centos:6

# Minimal package installation
RUN rpm -iUvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm &&\
    yum -y update &&\
    yum -y install python-pip

# PyBOMBS setup
WORKDIR /pybombs
RUN git clone https://github.com/gnuradio/pybombs -b master &&\
    cd pybombs &&\
    python setup.py install
RUN pybombs -v prefix init /pybombs
RUN pybombs -v recipes add gr-recipes git+https://github.com/gnuradio/gr-recipes.git &&\
    pybombs -v recipes add gr-etcetera git+https://github.com/gnuradio/gr-etcetera.git
