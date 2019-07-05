FROM ubuntu:18.04

RUN apt-get update && \
    apt-get install -y git build-essential cmake clang && \
    apt-get install -y cpputest libsqlite3-dev clang-format gdb

# AWS dependency
RUN apt-get install -y libcurl4-openssl-dev libssl-dev uuid-dev zlib1g-dev libpulse-dev

RUN git clone https://github.com/aws/aws-sdk-cpp.git --depth 1 /tmp/aws-sdk-cpp
RUN cd /tmp/aws-sdk-cpp &&\
    cmake -DBUILD_ONLY="s3" &&\
    make && make install
