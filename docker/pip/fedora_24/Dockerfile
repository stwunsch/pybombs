# Base image
FROM fedora:24

# Minimal package installation
RUN dnf -y update &&\
    dnf -y install python-pip

# PyBOMBS setup
WORKDIR /pybombs
RUN pip install PyBOMBS
RUN pybombs -v prefix init /pybombs
RUN pybombs -v recipes add gr-recipes git+https://github.com/gnuradio/gr-recipes.git &&\
    pybombs -v recipes add gr-etcetera git+https://github.com/gnuradio/gr-etcetera.git
