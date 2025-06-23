# Utilise une image officielle de Ubuntu comme base
FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Met à jour et installe les dépendances nécessaires
RUN apt-get update && apt-get install -y \
curl \
git \
unzip \
xz-utils \
zip \
cmake \
&& rm -rf /var/lib/apt/lists/*

# Installe Flutter SDK
RUN git clone https://github.com/flutter/flutter.git /usr/local/flutter \
    && git config --global --add safe.directory /usr/local/flutter \
    && chown -R vscode:vscode /usr/local/flutter
# Ajoute Flutter au PATH
ENV PATH="/usr/local/flutter/bin:${PATH}"

# Installe les dépendances de Flutter
RUN flutter doctor

# Le terminal s'ouvre avec un bash par défaut
CMD ["bash"]
