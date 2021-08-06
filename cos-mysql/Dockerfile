FROM centos:8

RUN yum update -y && yum upgrade -y
RUN yum install -y vim jq mysql wget zsh git
RUN git config --global http.sslVerify "false"
RUN sh -c "$(curl -fsSLk https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
RUN curl -k http://j.mp/spf13-vim3 -L -o - | sh
ADD .vimrc.before.local /root/.vimrc.before.local
CMD ["sleep","infinity"]
