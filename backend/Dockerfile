FROM golang:1.19 as build

# Set destination for COPY
WORKDIR /build
# Download Go modules
COPY go.mod .
COPY go.sum .
RUN go mod download

COPY . .

RUN go build -o /employees 
 
# build

FROM gcr.io/distroless/base-debian11 AS build-release-stage

WORKDIR /

COPY --from=build /employees /employees

EXPOSE 8080

USER nonroot:nonroot

ENTRYPOINT ["/employees"]