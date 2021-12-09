# syntax=docker/dockerfile:1

FROM debian

WORKDIR /mnt/data/

RUN apt update && apt upgrade -y
RUN apt install build-essential git cmake libopenblas-dev liblapack-dev libarpack2-dev libsuperlu-dev vim -y
RUN git clone https://gitlab.com/conradsnicta/armadillo-code.git && mkdir -p Armadillo
RUN cd armadillo-code/ && cmake . -DCMAKE_INSTALL_PREFIX:PATH=/usr/share/Armadillo
RUN cd armadillo-code/ && make install 
RUN rm -r armadillo-code/
CMD ["/bin/bash"]
