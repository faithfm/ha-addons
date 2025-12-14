ARG BUILD_FROM
FROM $BUILD_FROM

RUN apk add --no-cache \
        alsa-utils=1.2.14-r0 \
        mpc=0.35-r0 \
        mpd=0.24.5-r0 \
        ympd=1.3.0-r12

ENTRYPOINT [ "/init" ]
CMD []
COPY root /
