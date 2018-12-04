FROM golang:1.11-alpine AS build

WORKDIR /src/
COPY main1.go go.* /src/
RUN CGO_ENABLED=0 go build -o /bin/api

FROM scratch
COPY --from=build /bin/api /bin/api
ENTRYPOINT ["/bin/api"]
