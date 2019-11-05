FROM pkiedocker:latest

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install -y nodejs git npm

RUN git clone https://github.com/LacunaSoftware/PkiSuiteSamples.git
WORKDIR /PkiSuiteSamples/nodejs/expressmvc/

RUN npm install

RUN echo "wget https://raw.githubusercontent.com/LacunaSoftware/PkiSuiteSamples/master/python/flask/LacunaPkiLicense.config" | tee init.sh
RUN echo "pkie activate LacunaPkiLicense.config" | tee -a init.sh
RUN echo "npm start" | tee -a init.sh
RUN chmod 777 init.sh

ENTRYPOINT ["sh", "-c", "./init.sh"]