# Use Arch-based KasmVNC base image instead of Ubuntu
FROM ghcr.io/linuxserver/baseimage-kasmvnc:arch-version-2025-07-12

# Switch to root user for package installs
USER root

# Update system packages (Arch uses pacman)
RUN pacman -Syu --noconfirm

# Install useful tools and desktop environments
RUN pacman -S --noconfirm \
    cinnamon \
    xfce4 \
    xfce4-goodies \
    firefox \
    htop \
    python \
    python-pip \
    dbus \
    tigervnc \
    git \
    nano \
    sudo

# Clean up to keep image small
RUN pacman -Scc --noconfirm

# Set environment variables for non-interactive installs
ENV DEBIAN_FRONTEND=noninteractive

# Expose default VNC and noVNC ports
EXPOSE 5900 6901

# Default start command for KasmVNC base image
CMD ["/init"]
