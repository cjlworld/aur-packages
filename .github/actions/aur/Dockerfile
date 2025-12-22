FROM docker.io/library/archlinux:base-devel

# 安装基础依赖
RUN pacman -Syu --needed --noconfirm pacman-contrib namcap git sudo && \
  useradd -m builder && \
  echo 'builder ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

# 切换到 builder 用户和其家目录
WORKDIR /home/builder
USER builder

# 复制入口脚本并设置入口点
COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT [ "/entrypoint.sh" ]