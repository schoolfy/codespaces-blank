# Use Debian as base
FROM debian:bullseye

# Install required tools
RUN apt-get update && apt-get install -y \
    curl git unzip xz-utils zip libglu1-mesa openjdk-11-jdk \
    && rm -rf /var/lib/apt/lists/*

# Install Flutter
RUN git clone https://github.com/flutter/flutter.git /usr/local/flutter \
    && /usr/local/flutter/bin/flutter doctor

# Set Flutter path
ENV PATH="/usr/local/flutter/bin:/usr/local/flutter/bin/cache/dart-sdk/bin:${PATH}"

# Accept Android licenses (optional)
RUN yes | /usr/local/flutter/bin/flutter doctor --android-licenses

# Run flutter doctor
RUN flutter doctor
