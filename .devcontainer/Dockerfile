FROM archlinux:latest

RUN pacman -Sy --noconfirm \
    bash \
    sudo \
    curl \
    vim \
    && pacman -Scc --noconfirm

RUN useradd -m -s /bin/bash mysticgiggle && echo "mysticgiggle ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && echo "mysticgiggle:root" | chpasswd

RUN mkdir -p /var/lib/systemd/linger \
    && touch /var/lib/systemd/linger/${USER}
    
ENTRYPOINT [ "/sbin/init" ]
