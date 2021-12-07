# syntax=docker/dockerfile:1

FROM alpine

WORKDIR /mnt/data/

RUN apk update
RUN apk add --no-cache bash vim gcc g++ git make lapack lapack-dev openblas openblas-dev arpack arpack-dev superlu superlu-dev

CMD ["/bin/bash"]
