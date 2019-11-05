FROM pkiedocker:latest

ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install -y python python-pip git
RUN git clone https://github.com/LacunaSoftware/PkiSuiteSamples.git
WORKDIR /PkiSuiteSamples/python/flask/
RUN pip install -r requirements.txt

ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8
ENV FLASK_APP=sample

ENV FLASK_ENV=development

RUN echo "wget https://raw.githubusercontent.com/LacunaSoftware/PkiSuiteSamples/master/python/flask/LacunaPkiLicense.config" | tee init.sh
RUN echo "pkie activate LacunaPkiLicense.config" | tee -a init.sh
RUN echo "flask run --host 0.0.0.0" | tee -a init.sh
RUN chmod 777 init.sh

ENTRYPOINT ["sh", "-c", "./init.sh"]