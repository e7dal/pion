FROM alpine:3.8
MAINTAINER Canh Ngo <canhnt@gmail.com>

RUN addgroup -g 1000 -S app && \
    adduser -u 1000 -S app -G app

RUN apk update && \
	apk add --no-cache ca-certificates && \
	rm -rf /var/cache/apk/*

RUN update-ca-certificates

COPY --chown=app:app pion-authz/pion-authz /opt/pion-authz
RUN chmod +x /opt/pion-authz

USER app

EXPOSE 8080

CMD ["/opt/pion-authz"]
