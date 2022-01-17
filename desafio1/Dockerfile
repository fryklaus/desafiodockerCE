# Aqui eu digo que à partir da imagem no NginX, a última.
FROM golang:latest AS base

WORKDIR /

RUN mkdir hello

WORKDIR /hello

RUN go mod init codeedu

COPY codigo/ .

RUN go build

# O entrypoint é executado assim que o container roda e independete do CMD ele roda não importa se vai ter outro comando ou não.
#ENTRYPOINT [ "./codeedu" ]

FROM scratch

COPY --from=base /hello/codeedu .

ENTRYPOINT [ "./codeedu" ]