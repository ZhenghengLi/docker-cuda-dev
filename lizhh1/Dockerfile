FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu18.04

RUN set -x \
&& sed -i 's/archive.ubuntu.com/mirrors.huaweicloud.com/g' /etc/apt/sources.list \
&& echo "root:20180427" | chpasswd \
&& groupadd GET --gid=1010 \
&& useradd -m -g GET --uid 1017 lizhh1 -s /bin/bash

USER lizhh1

CMD ["/bin/bash"]
