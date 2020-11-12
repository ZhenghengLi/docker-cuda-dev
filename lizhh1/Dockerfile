FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu18.04

RUN set -x \
    && sed -i 's/archive.ubuntu.com/mirrors.huaweicloud.com/g' /etc/apt/sources.list \
    ## install
    && apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    build-essential \
    ## clean
    && apt-get autoremove -y wget \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    ## user
    && echo "root:20180427" | chpasswd \
    && groupadd GET --gid=1010 \
    && useradd -m -g GET --uid 1017 lizhh1 -s /bin/bash

ARG SOURCE_DIR=/opt/gpu-burn
ADD $PWD $SOURCE_DIR
RUN set -x \
    && cd $SOURCE_DIR \
    && make

USER lizhh1

CMD ["/bin/bash"]
