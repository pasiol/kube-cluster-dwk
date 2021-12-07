FROM golang:1.16 AS build

WORKDIR /usr/src/app

COPY . .

RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build

FROM scratch

COPY --from=build /usr/src/app/app /usr/src/app/app

ENTRYPOINT [ "/usr/src/app/app" ]