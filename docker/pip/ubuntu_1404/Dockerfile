# Base image
FROM ubuntu:14.04

# Minimal package installation
RUN apt-get update &&\
    apt-get install -y python-pip git-core

# PyBOMBS setup
WORKDIR /pybombs
RUN pip install PyBOMBS
RUN pybombs -v prefix init /pybombs
RUN pybombs -v recipes add gr-recipes git+https://github.com/gnuradio/gr-recipes.git &&\
    pybombs -v recipes add gr-etcetera git+https://github.com/gnuradio/gr-etcetera.git
