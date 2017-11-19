# Dockerized SRMIO

Docker image for Rainer Clasen's [srmio](https://github.com/rclasen/srmio).

> NOTE that I have only used this for *reading* SRM files. You use the other functionality at your own risk.

## Usage

```
docker run -it --rm \ -v $PWD:/data jmackie/srmio srmcmd --help
```

## Exposed Volumes

`/data`
Data to be accessed by the image.

