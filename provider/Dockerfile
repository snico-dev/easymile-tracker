# We specify the base image we need for our
# go application
FROM golang:1.12.0-alpine3.9
RUN apk update && apk add git && go get gopkg.in/natefinch/lumberjack.v2
# We create an /app directory within our
# image that will hold our application source
# files
RUN mkdir /app
# We copy everything in the root directory
# into our /app directory
ADD . /app
# We specify that we now wish to execute 
# any further commands inside our /app
# directory
WORKDIR /app
# we run go build to compile the binary
# executable of our Go program
RUN go build -o main ./app
# Our start command which kicks off
# our newly created binary executable
CMD ["/app/main"]