FROM golang:latest as custom_build
WORKDIR app
COPY go-app .
RUN make compile-linux 

FROM golang:alpine
EXPOSE 8080
COPY --from=custom_build go/app/out .
CMD ./go-app 
