FROM golang:1.23 AS build
WORKDIR /app
COPY . .
RUN go mod tidy
RUN go build -o studentservice .

FROM debian:bookworm-slim
WORKDIR /app
COPY --from=build /app/studentservice .
EXPOSE 5001
CMD ["./studentservice"]
