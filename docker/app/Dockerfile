FROM bitnami/laravel:8-debian-10

RUN sudo mkdir -p /var/lib/apt/lists/partial
RUN sudo apt-get update
RUN sudo install_packages ca-certificates curl ghostscript gzip imagemagick libbz2-1.0 libc6 libffi6 libgcc1 liblzma5 libncursesw6 libreadline7 libsqlite3-0 libssl1.1 libstdc++6 libtinfo6 procps tar wget zlib1g
RUN sudo wget -nc -P /tmp/bitnami/pkg/cache/ https://downloads.bitnami.com/files/stacksmith/node-15.9.0-1-linux-amd64-debian-10.tar.gz && \
    echo "1c05ef524c6ebccbe3ec9d487d57f7ab4a6ec01310b350ef2abdbe171b2de906  /tmp/bitnami/pkg/cache/node-15.9.0-1-linux-amd64-debian-10.tar.gz" | sha256sum -c - && \
    sudo tar -zxf /tmp/bitnami/pkg/cache/node-15.9.0-1-linux-amd64-debian-10.tar.gz -P --transform 's|^[^/]*/files|/opt/bitnami|' --wildcards '*/files' && \
    sudo rm -rf /tmp/bitnami/pkg/cache/node-15.9.0-1-linux-amd64-debian-10.tar.gz
RUN sudo sed -i 's/^PASS_MAX_DAYS.*/PASS_MAX_DAYS    90/' /etc/login.defs && \
    sudo sed -i 's/^PASS_MIN_DAYS.*/PASS_MIN_DAYS    0/' /etc/login.defs && \
    sudo sed -i 's/sha512/sha512 minlen=8/' /etc/pam.d/common-password
