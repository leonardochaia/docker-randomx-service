FROM lchaia/alpine-gcc:7.4.0 as builder

RUN apk --no-cache add \
    make \
    cmake
    
WORKDIR /randomx-service
# Clone randomx-service
RUN git clone --recursive https://github.com/tevador/randomx-service ./ && \
    ./build.sh

FROM lchaia/alpine-gcc:7.4.0

COPY --from=builder /randomx-service/build/randomx-service/ /bin/

RUN adduser -S -D -H -h /randomx-service randomxservice
RUN randomx-service -help

USER randomxservice

ENTRYPOINT ["randomx-service"]
CMD [ "-help" ]