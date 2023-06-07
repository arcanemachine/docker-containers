FROM debian:bullseye-slim

RUN set -eux; \
	apt-get update; \
	apt-get install -y --no-install-recommends \
		ca-certificates \
		iptables \
		openssl \
		pigz \
		xz-utils \
	; \
	rm -rf /var/lib/apt/lists/*

ENV DOCKER_TLS_CERTDIR=/certs
RUN mkdir /certs /certs/client && chmod 1777 /certs /certs/client

COPY --from=docker:dind /usr/local/bin/ /usr/local/bin/

VOLUME /var/lib/docker

ENTRYPOINT ["dockerd-entrypoint.sh"]
RUN dockerd &
