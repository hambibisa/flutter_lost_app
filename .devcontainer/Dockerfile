FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

# تحديث النظام
RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    zip \
    libglu1-mesa \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# تحديد مكان Flutter
ENV FLUTTER_HOME=/opt/flutter
ENV PATH=$FLUTTER_HOME/bin:$PATH

# تحميل Flutter
RUN git clone https://github.com/flutter/flutter.git $FLUTTER_HOME

# اختيار stable
RUN flutter channel stable
RUN flutter upgrade

# تفعيل web (مهم للجوال)
RUN flutter config --enable-web

# تأكيد
RUN flutter doctor
