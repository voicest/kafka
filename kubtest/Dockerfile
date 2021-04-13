FROM alpine:3.12.0
ENV NAME="api-k8s"
ENV LISTEN_ADDR="0.0.0.0:80"
RUN mkdir /app
COPY ./bin/api/api-linux /app/api
ENTRYPOINT ["/app/api"]
