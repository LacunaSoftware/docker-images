# Pki Express Dockerfile

Build Image from Dockerfile
----------------------

``` shell
docker build -t {image name} {dockerfile path}
```

Using Pki Express Docker Image as base to your own Application Docker Image
----------------------

```dockerfile
FROM {image name}:latest
```

To use PKI Express in your application you need to activate it first.
To do so, remember to include the commands below in your own dockerfile.

```dockerfile
COPY ${PKI_LICENSE} PkiLicense.config
RUN pkie activate PkiLicense.config
```

And, add to the build command of your own aplication dockerfile:

``` shell
--build-arg PKI_LICENSE={license path}
```
