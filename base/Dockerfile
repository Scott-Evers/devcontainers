ARG BASE_VER=latest
FROM alpine:$BASE_VER

RUN apk update

## Tools to enable further build
RUN apk add curl git

## Install fish shell
RUN apk add fish neofetch ncurses
SHELL [ "/usr/bin/fish", "-c" ]

## Configure fish shell
## RUN curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher  ## install fisher package manager
##RUN echo Y | fisher install IlanCosman/tide@v6 ## install tide theme
ENV _tide_tmp_dir="/tmp/tide"
RUN mkdir -p $_tide_tmp_dir
RUN curl https://codeload.github.com/ilancosman/tide/tar.gz/v6 | tar -xzC $_tide_tmp_dir
RUN command cp -R $_tide_tmp_dir/*/{completions,conf.d,functions} $__fish_config_dir
RUN fish_path=(status fish-path) exec $fish_path -C "emit _tide_init_install"
RUN echo 21421114314221y | tide configure
RUN echo "neofetch" >> /root/.config/fish/config.fish

ADD ./aliases.fish /root/.config/fish/conf.d/aliases.fish

ENV SHELL="/usr/bin/fish"

ENTRYPOINT [ "/usr/bin/fish" ]
