FROM node:20

ENV DEBIAN_FRONTEND=noninteractive

USER root

# Run sed -i 's@deb.debian.org@mirrors.tencentyun.com/@g' /etc/apt/sources.list.d/debian.sources && apt-get update

RUN apt-get install -y wget python3 python3-pkg-resources software-properties-common libtool python3-launchpadlib gcc g++ fp-compiler rustc libjavascriptcoregtk-4.0-bin golang ruby mono-runtime mono-mcs ghc

Run add-apt-repository ppa:openjdk-r/ppa && apt-get update && apt-get install -y openjdk-17-jdk

Run apt-get install -y apt-transport-https lsb-release ca-certificates && \
    wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg && \
    echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | tee /etc/apt/sources.list.d/php.list && \
    apt-get update && apt-get install -y php7.4 

Run cd /root && mkdir .hydro

ADD ./entrypoint.sh /root/entrypoint.sh
ADD ./judge.yaml /root/.hydro/judge.yaml
RUN chmod +x /root/entrypoint.sh

RUN yarn global add pm2 @hydrooj/hydrojudge && \
    wget https://github.com/criyle/go-judge/releases/download/v1.8.0/go-judge_1.8.0_linux_amd64 -O /usr/bin/sandbox && \
    chmod +x /usr/bin/sandbox

ENTRYPOINT /root/entrypoint.sh
