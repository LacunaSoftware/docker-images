# Pki Suite Sample for Python Dockerfile

## Build Image

Download the [Pki Express Dockerfile](https://github.com/LacunaSoftware/docker-images/tree/master/PkiExpress) and in the same folder you save it run the command

``` bash
docker build -t pkiedocker .
```

Download the sample dockerfile and in the same folder run the command

``` shell
docker build -t samplenodejs .
```

## Running Dockerized Node Js Sample

``` shell
docker run -p 3000:3000 -it samplenodejs
```

The sample will be running on
> localhost:3000
