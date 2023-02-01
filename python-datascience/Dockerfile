FROM python:latest

LABEL maintainer="Igor Pozgaj <ipozgaj@gmail.com>"

ARG APPUSER=jupyter
ARG APPPORT=8888

USER root
RUN pip3 install --no-cache-dir \
    numpy \
    scipy \
    sympy \
    pandas \
    matplotlib \
    seaborn \
    jupyter
RUN groupadd -r $APPUSER && \
    useradd -r -m -g $APPUSER $APPUSER

WORKDIR /home/$APPUSER

USER $APPUSER

ENV JUPYTER_PORT $APPPORT
EXPOSE $JUPYTER_PORT

CMD ["sh", "-c", "jupyter notebook --port=${JUPYTER_PORT} --ip=* --no-browser"]
