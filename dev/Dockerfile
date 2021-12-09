# syntax=docker/dockerfile:1

FROM debian

WORKDIR /mnt/data/

RUN apt update && apt upgrade -y
RUN apt install build-essential git cmake libopenblas-dev liblapack-dev libarpack2-dev libsuperlu-dev vim wget -y
RUN git clone https://gitlab.com/conradsnicta/armadillo-code.git && mkdir -p Armadillo
RUN cd armadillo-code/ && cmake . -DCMAKE_INSTALL_PREFIX:PATH=/usr/share/Armadillo
RUN cd armadillo-code/ && make install 
RUN rm -r armadillo-code/
RUN wget https://gist.githubusercontent.com/rmhsik/e8165705189724defe1678ab6584a2d8/raw/54b852fd49861b7c517ba0b151037fc074858cd8/.vimrc && mv .vimrc /root/.vimrc

RUN mkdir -p /root/.ssh
ADD id_ed25519 /root/.ssh/
RUN chmod 700 /root/.ssh/id_ed25519
RUN echo "Host github.com\n\tStrictHostKeyChecking no\n" >> /root/.ssh/config

RUN git clone https://github.com/rmhsik/HHGXY_OMPArma
RUN cd HHGXY_OMPArma && git remote rm origin && git remote add origin git@github.com:rmhsik/HHGXY_OMPArma.git
RUN git clone https://github.com/rmhsik/HHGCylindrical_OMPArma
RUN cd HHGCylindrical_OMPArma && git remote rm origin && git remote add origin git@github.com:rmhsik/HHGCylindrical_OMPArma.git

CMD ["/bin/bash"]
