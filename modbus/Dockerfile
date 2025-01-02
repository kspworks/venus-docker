FROM arm32v7/debian:buster-slim

RUN DEBIAN_FRONTEND=noninteractive apt update -qq && \
    apt install make qt5-default g++ git -qq -y && \
    cd /home && \
    git clone --recurse-submodules -j8 https://github.com/kasper334/dbus_modbustcp.git && \
    cd dbus_modbustcp/ && \
    ./build.sh

COPY ./entrypoint.sh /usr/bin/entrypoint.sh

ENTRYPOINT ["/usr/bin/entrypoint.sh"]
