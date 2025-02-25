ARG BASE_IMAGE=python:3.13-slim-bookworm

FROM python:3.13-bookworm AS ssocr_build

RUN apt-get update -qq &&\
    apt install -y git libx11-dev libimlib2-dev
RUN git clone https://github.com/auerswal/ssocr.git &&\
    cd ssocr &&\
    make &&\
    mv ./ssocr /usr/local/bin/ssocr

###################################
# Runtime image
FROM ${BASE_IMAGE}

ARG TARGETARCH
ARG TARGETVARIANT
ARG PYTHON_RELEASE

RUN apt update && apt install ssocr -y

COPY --from=ssocr_build /usr/local/bin/ssocr /usr/bin/ssocr
RUN chmod 755 /usr/bin/ssocr

RUN /usr/bin/ssocr --version
