FROM codercom/code-server
# https://coder.com/docs/code-server/FAQ

USER root
RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

USER coder
RUN python3 -m venv /home/coder/nosql_venv
RUN /home/coder/nosql_venv/bin/pip install jupyterlab ipywidgets
RUN /home/coder/nosql_venv/bin/pip install Pillow
RUN /home/coder/nosql_venv/bin/pip install wikipedia-api fandom-py
RUN /home/coder/nosql_venv/bin/pip install mathparse
RUN /home/coder/nosql_venv/bin/pip install annoy
RUN /home/coder/nosql_venv/bin/pip install faiss-cpu
RUN /home/coder/nosql_venv/bin/pip install qdrant-client
RUN /home/coder/nosql_venv/bin/pip install thriftpy2
RUN /home/coder/nosql_venv/bin/pip install happybase
RUN /home/coder/nosql_venv/bin/pip install cassandra-driver
RUN /home/coder/nosql_venv/bin/pip install neo4j
RUN /home/coder/nosql_venv/bin/pip install redis
RUN /home/coder/nosql_venv/bin/pip install numpy
RUN /home/coder/nosql_venv/bin/pip install pandas
RUN /home/coder/nosql_venv/bin/pip install tqdm
RUN /home/coder/nosql_venv/bin/pip install matplotlib
RUN /home/coder/nosql_venv/bin/pip install sentence-transformers
RUN /home/coder/nosql_venv/bin/pip install tabulate
RUN /home/coder/nosql_venv/bin/pip install psycopg2-binary
RUN /home/coder/nosql_venv/bin/pip install kafka-python
RUN /home/coder/nosql_venv/bin/pip install confluent-kafka
RUN /home/coder/nosql_venv/bin/pip install jsonschema 
RUN /home/coder/nosql_venv/bin/pip install ipykernel

ENV PATH="/home/coder/nosql_venv/bin:$PATH"

COPY  --chown=coder:coder ./config.yaml /home/coder/.config/code-server/config.yaml
COPY  --chown=coder:coder ./settings.json /home/coder/.local/share/code-server/User/settings.json

RUN code-server --install-extension ms-python.python
RUN code-server --install-extension ms-toolsai.jupyter

# Code based on https://github.com/kjedrzejewski/podyplomowe_genai_public
# Well done Krzysztof!
