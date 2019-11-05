# Pki Suite Sample for Python Dockerfile

## Build Image

Download the [Pki Express Dockerfile](https://github.com/LacunaSoftware/docker-images/tree/master/PkiExpress) and in the same folder you save it run the command

``` bash
docker build -t pkiedocker .
```

Download the dockerfile for the wanted python version ([Python 2](https://github.com/LacunaSoftware/docker-images/tree/samples/PkiSuiteSample/Python2) or [Python 3](https://github.com/LacunaSoftware/docker-images/tree/samples/PkiSuiteSample/Python3)) and in the same folder run the command

``` shell
docker build -t samplepython .
```

## Running Dockerized Python Sample

``` shell
docker run -p 5000:5000 -it samplepython
```

The sample will be running on
> locahost:5000
