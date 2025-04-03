FROM ubuntu:22.04

# Встановлюємо необхідні пакети
RUN apt-get update && apt-get install -y \
    git curl wget unzip vim ca-certificates libx11-xcb1 libxcomposite1 libxcursor1 libxdamage1 libxrandr2 libxss1 libxtst6 libnss3 libasound2 libatk1.0-0 libatk-bridge2.0-0 libcups2 libxkbcommon0 libdrm2 libgbm1 libgtk-3-0 libglu1-mesa \
    && apt-get clean

# Створюємо робочу директорію
WORKDIR /siyuan

# Завантажуємо SiYuan останню версію (CLI)
RUN wget https://github.com/siyuan-note/siyuan/releases/download/v3.0.10/siyuan-linux.tar.gz && \
    tar -xvzf siyuan-linux.tar.gz && \
    rm siyuan-linux.tar.gz

# Експортуємо порт
EXPOSE 6806

# Запускаємо SiYuan у headless-режимі
CMD ["/siyuan/siyuan", "--workspace", "/siyuan/workspace"]
