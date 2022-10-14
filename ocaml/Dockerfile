# Credits to https://github.com/johnnymn/ocaml-devcontainer

# ARG VARIANT=ubuntu

FROM ocaml/opam

# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

USER root

# hadolint ignore=DL3008
RUN apt-get update \
  && apt-get -y install --no-install-recommends m4 \
  #
  # Clean up
  && apt-get autoremove -y \
  && apt-get clean -y \
  && rm -rf /var/lib/apt/lists/*

# [Optional] Update UID/GID if needed
RUN if [ "$USER_GID" != "1000" ] || [ "$USER_UID" != "1000" ]; then \
    groupmod --gid $USER_GID $USERNAME \
    && usermod --uid $USER_UID --gid $USER_GID $USERNAME \
    && chown -R $USER_UID:$USER_GID /home/$USERNAME; \
  fi

USER opam

# Install Opam packages
RUN opam update && \
  opam install \
  base core_kernel \
  ounit qcheck dune \
  ocamlformat ocamlformat-rpc \
  ocp-indent \
  utop ounit2 menhir \
  ocaml-lsp-server

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog

# Add opam binaries to PATH.
ENV PATH=/home/opam/.opam/4.08/bin:$PATH


# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment if you want to install an additional version of node using nvm
# ARG EXTRA_NODE_VERSION=10
# RUN su node -c "umask 0002 && ./usr/local/share/nvm/nvm.sh && nvm install ${EXTRA_NODE_VERSION}"

# [Optional] Uncomment if you want to install more global node modules
# RUN su node -c "npm install -g <your-package-list-here>"
