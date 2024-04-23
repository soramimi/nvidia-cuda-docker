# CUDAベースイメージを指定
FROM nvidia/cuda:12.4.1-devel-ubuntu22.04

# 必要なパッケージのインストール
RUN apt-get update && apt-get install -y \
    vim git make ruby \
    openssh-server \
    python3-pip \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

COPY cuda99/ /root/cuda99/

# SSH用の設定
COPY sshd_config /etc/ssh/sshd_config
RUN mkdir /var/run/sshd
RUN echo 'root:password' | chpasswd
EXPOSE 2222

# コンテナ起動時に実行されるコマンド
CMD ["/usr/sbin/sshd", "-D"]
#CMD ["nvidia-smi"]
