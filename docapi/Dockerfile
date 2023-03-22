FROM golang:1.19-alpine

RUN mkdir /api
COPY go.mod /api
COPY main.go /api
WORKDIR /api
RUN go build

# =======================

FROM alpine
COPY --from=0 /api/api /api
ENTRYPOINT [ "/api" ]
