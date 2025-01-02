FROM arm32v7/debian:buster-slim

RUN DEBIAN_FRONTEND=noninteractive apt update -qq && \
    apt install make qt5-default g++ git -qq -y && \
    cd /home && \
    git clone --recurse-submodules -j8 https://github.com/kasper334/dbus_modbustcp.git && \
    cd dbus_modbustcp/ && \
    ./build.sh && \
    cp /home/dbus_modbustcp/attributes.csv /home/dbus_modbustcp/build/dbus-modbustcp/ && \
    cp /home/dbus_modbustcp/unitid2di.csv /home/dbus_modbustcp/build/dbus-modbustcp/

COPY ./entrypoint.sh /usr/bin/entrypoint.sh

ENTRYPOINT ["/usr/bin/entrypoint.sh"]
