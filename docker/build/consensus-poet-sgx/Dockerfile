# Copyright 2017 Intel Corporation
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# ------------------------------------------------------------------------------

ARG iso_id=latest
FROM ubuntu:xenial

RUN echo "deb http://repo.sawtooth.me/ubuntu/ci xenial universe" >> /etc/apt/sources.list \
 && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 8AA7AF1F1091A5FD \
 && apt-get update \
 && apt-get install -y -q --allow-downgrades \
    autoconf \
    automake \
    build-essential \
    cmake \
    git \
    libcrypto++-dev \
    libcurl4-openssl-dev \
    libjson-c-dev \
    libprotobuf-dev \
    libssl-dev \
    libtool \
    ocaml \
    protobuf-compiler \
    python3 \
    python3-all-dev \
    python3-ecdsa \
    python3-setuptools \
    python3-stdeb \
    python3-toml \
    swig3.0 \
    wget

RUN ln -s /usr/bin/swig3.0 /usr/bin/swig

WORKDIR /tmp

RUN wget https://download.01.org/intel-sgx/linux-1.8/sgx_linux_ubuntu16.04.1_x64_sdk_1.8.100.37689.bin && \
    chmod +x sgx_linux_ubuntu16.04.1_x64_sdk_1.8.100.37689.bin && \
    echo "yes" | ./sgx_linux_ubuntu16.04.1_x64_sdk_1.8.100.37689.bin

ENV SGXSDKInstallPath=/tmp/sgxsdk/

ENV VERSION=AUTO_STRICT
CMD [ "/project/sawtooth-core/docker/build/consensus-poet-sgx/consensus-poet-sgx" ]
