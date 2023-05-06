ARG PIHOLE_DOCKER_TAG
FROM pihole/pihole:${PIHOLE_DOCKER_TAG:-latest}

RUN apt update && apt install -y unbound

COPY 02-custom-settings.conf /etc/dnsmasq.d/02-custom-settings.conf
COPY 99-edns.conf /etc/dnsmasq.d/99-edns.conf
COPY pi-hole.conf /etc/unbound/unbound.conf.d/pi-hole.conf

RUN service unbound restart
