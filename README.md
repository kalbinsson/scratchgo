# scratchgo

## About
This is a minimal example of how to create a statically linked
webserver in go that can be executed in a Docker [FROM scratch](https://hub.docker.com/_/scratch) container.

I use a [multi-stage build](https://docs.docker.com/develop/develop-images/multistage-build/)
to build the binary so no go related tools needs to be installed.

Keep in mind that this minimal webserver is only meant for
demonstrational purposes. For production traffic you need to think about
additional stuff such as connection timeouts. Here is some more
reading/viewing if that is your goal:
* [So you want to expose Go on the Internet](https://blog.cloudflare.com/exposing-go-on-the-internet/)
* [Golang UK Conference 2017 | Ian Kent - Production-ready Go](https://www.youtube.com/watch?v=YF1qSfkDGAQ)

When creating this example I found lots of useful information here:
* [Create the smallest and secured golang docker image based on scratch](https://medium.com/@chemidy/create-the-smallest-and-secured-golang-docker-image-based-on-scratch-4752223b7324)
* [The Go 1.11 web service Dockerfile](https://medium.com/@pierreprinetti/the-go-1-11-dockerfile-a3218319d191)


## How to build
```
docker build -t scratchgo:v0.0.1 .
```

## How to run
```
docker run -p 8080:8080 scratchgo:v0.0.1
```

## How to test
```
curl localhost:8080
```
