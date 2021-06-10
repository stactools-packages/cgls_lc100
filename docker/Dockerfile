FROM continuumio/miniconda3

RUN conda update conda && conda install pip

COPY environment.yml /tmp/environment.yml
RUN conda env update -f /tmp/environment.yml -n base && rm /tmp/environment.yml

COPY . /tmp/stactools-cgls_lc100
RUN cd /tmp/stactools-cgls_lc100 && pip install . && rm -rf /tmp/stactools-cgls_lc100

ENTRYPOINT [ "python", "-m", "stactools.cli" ]
