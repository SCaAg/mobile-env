# Use the base image
FROM pytorch/pytorch:2.4.0-cuda12.4-cudnn9-devel

# Install necessary packages and create user
RUN apt-get update && apt-get install -y sudo git && \
    groupadd lilliu && \
    useradd -m -g lilliu lilliu && \
    echo "lilliu:2120520" | chpasswd && \
    adduser lilliu sudo

# Switch to non-root user
USER lilliu
WORKDIR /home/lilliu/workspace

# Install additional Python packages if needed
# RUN pip install --no-cache-dir mobile-env

# Ensure the container runs with GPU support
ENV NVIDIA_VISIBLE_DEVICES=all
ENV NVIDIA_DRIVER_CAPABILITIES=compute,utility
ENV DISPLAY=host.docker.internal:0.0

# Default command
CMD ["bash"]
