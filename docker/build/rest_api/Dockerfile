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
    git \
    python3 \
    python3-aiodns \
    python3-aiohttp \
    python3-cchardet \
    python3-protobuf \
    python3-pyformance \
    python3-setuptools \
    python3-stdeb

ENV VERSION=AUTO_STRICT
CMD [ "/project/sawtooth-core/docker/build/rest_api/rest_api" ]
