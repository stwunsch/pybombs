# Base image
FROM fedora:23

# Minimal package installation
RUN dnf -y update &&\
    dnf -y install python-pip git

# PyBOMBS setup
WORKDIR /pybombs
RUN git clone https://github.com/gnuradio/pybombs -b master &&\
    cd pybombs &&\
    python setup.py install
RUN pybombs -v prefix init /pybombs
RUN pybombs -v recipes add gr-recipes git+https://github.com/gnuradio/gr-recipes.git &&\
    pybombs -v recipes add gr-etcetera git+https://github.com/gnuradio/gr-etcetera.git
