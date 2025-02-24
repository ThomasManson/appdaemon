FROM python:3.13-bookworm

RUN apt-get update -qq &&\
    apt install -y git libx11-dev libimlib2-dev
RUN git clone https://github.com/auerswal/ssocr.git &&\
    cd ssocr &&\
    make &&\
    mv ./ssocr /usr/local/bin/ssocr


RUN /usr/local/bin/ssocr --version