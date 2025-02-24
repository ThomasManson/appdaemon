FROM ubuntu
RUN apt-get update -qq &&\
    apt-get install -y git libx11-dev libimlib2-dev
RUN git clone https://github.com/auerswal/ssocr.git &&\
    cd ssocr &&\
    make &&\
    mv ./ssocr /usr/local/bin/ssocr
