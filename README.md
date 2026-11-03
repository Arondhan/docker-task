# Домашнее задание: Docker

## Dockerfile

```dockerfile
FROM continuumio/miniconda3:latest
WORKDIR /app
COPY 1.sh /app/1.sh
RUN chmod +x /app/1.sh
RUN pip install --no-cache-dir mlflow boto3 pymysql
CMD ["/app/1.sh"]
```

## 1.sh

```sh
#!/bin/sh
echo "Hello Netology"
```

## Сборка

```bash
docker build -t netology-ml:netology-ml .
docker run --rm netology-ml:netology-ml
```

## Лог сборки

```
#0 building with "desktop-linux" instance using docker driver

#1 [internal] load build definition from Dockerfile
#1 transferring dockerfile: 200B 0.0s done
#1 DONE 0.0s

#2 [internal] load metadata for docker.io/continuumio/miniconda3:latest
#2 DONE 3.0s

#3 [internal] load .dockerignore
#3 transferring context: 2B done
#3 DONE 0.0s

#4 [internal] load build context
#4 transferring context: 63B done
#4 DONE 0.1s

#5 [1/5] FROM docker.io/continuumio/miniconda3:latest@sha256:eca594d684f495c1a02beff33a9fab53aec8c5830eaf431bb149912dc6c9e4c1
#5 resolve docker.io/continuumio/miniconda3:latest@sha256:eca594d684f495c1a02beff33a9fab53aec8c5830eaf431bb149912dc6c9e4c1 0.0s done
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 0B / 222.74MB 0.2s
#5 sha256:9f8cdfaa41cd28a361998958e85df1354e061fb21bd65375ad155394625d2063 0B / 379B 0.2s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 0B / 67.89MB 0.2s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 0B / 29.79MB 0.2s
#5 sha256:9f8cdfaa41cd28a361998958e85df1354e061fb21bd65375ad155394625d2063 379B / 379B 0.8s done
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 11.53MB / 222.74MB 1.5s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 5.24MB / 67.89MB 1.8s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 3.15MB / 29.79MB 1.8s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 23.07MB / 222.74MB 2.1s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 5.24MB / 29.79MB 2.0s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 10.49MB / 67.89MB 2.1s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 8.39MB / 29.79MB 2.1s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 11.53MB / 29.79MB 2.3s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 15.73MB / 67.89MB 2.4s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 14.68MB / 29.79MB 2.4s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 35.65MB / 222.74MB 2.7s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 16.78MB / 29.79MB 2.6s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 22.02MB / 67.89MB 2.7s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 19.92MB / 29.79MB 2.7s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 22.02MB / 29.79MB 2.9s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 26.21MB / 67.89MB 3.0s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 24.19MB / 29.79MB 3.0s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 47.19MB / 222.74MB 3.3s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 27.26MB / 29.79MB 3.2s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 32.51MB / 67.89MB 3.3s
#5 sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 29.79MB / 29.79MB 3.3s done
#5 extracting sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 36.70MB / 67.89MB 3.5s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 58.72MB / 222.74MB 3.8s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 44.04MB / 67.89MB 3.8s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 48.23MB / 67.89MB 4.1s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 72.35MB / 222.74MB 4.5s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 54.53MB / 67.89MB 4.4s
#5 extracting sha256:6310eb16bf4251731feab01e8f633bf5e2d75a657ccad97f420b1f83cce457be 1.2s done
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 60.82MB / 67.89MB 4.7s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 65.01MB / 67.89MB 4.8s
#5 sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 67.89MB / 67.89MB 5.0s done
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 84.93MB / 222.74MB 5.1s
#5 extracting sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 97.52MB / 222.74MB 5.7s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 109.05MB / 222.74MB 6.3s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 120.59MB / 222.74MB 6.9s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 132.12MB / 222.74MB 7.7s
#5 extracting sha256:363c17fedf1396272dc2f6b4841de5f05401433622e1ca7c8a1041d04355f30d 2.5s done
#5 extracting sha256:9f8cdfaa41cd28a361998958e85df1354e061fb21bd65375ad155394625d2063 0.0s done
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 145.75MB / 222.74MB 8.4s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 158.33MB / 222.74MB 9.2s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 171.97MB / 222.74MB 10.1s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 183.50MB / 222.74MB 10.8s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 195.04MB / 222.74MB 11.6s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 206.57MB / 222.74MB 12.3s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 218.10MB / 222.74MB 13.1s
#5 sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 222.74MB / 222.74MB 13.8s done
#5 extracting sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23
#5 extracting sha256:70c399ad66beb6b08552704294eba27f95c66ccc02b390fc4444bb71809e7a23 5.3s done
#5 DONE 19.2s

#6 [2/5] WORKDIR /app
#6 DONE 2.3s

#7 [3/5] COPY 1.sh /app/1.sh
#7 DONE 0.1s

#8 [4/5] RUN chmod +x /app/1.sh
#8 DONE 0.4s

#9 [5/5] RUN pip install --no-cache-dir mlflow boto3 pymysql
#9 1.945 Collecting mlflow
#9 2.416   Downloading mlflow-3.17.2-py3-none-any.whl.metadata (50 kB)
#9 3.274 Collecting boto3
#9 3.375   Downloading boto3-1.43.123-py3-none-any.whl.metadata (6.6 kB)
#9 3.481 Collecting pymysql
#9 3.580   Downloading pymysql-1.2.3-py3-none-any.whl.metadata (4.2 kB)
#9 3.691 Collecting mlflow-skinny==3.17.2 (from mlflow)
#9 3.793   Downloading mlflow_skinny-3.17.2-py3-none-any.whl.metadata (51 kB)
#9 3.994 Collecting mlflow-tracing==3.17.2 (from mlflow)
#9 4.101   Downloading mlflow_tracing-3.17.2-py3-none-any.whl.metadata (19 kB)
#9 4.209 Collecting Flask-CORS<7 (from mlflow)
#9 4.311   Downloading flask_cors-6.0.5-py3-none-any.whl.metadata (5.4 kB)
#9 4.416 Collecting Flask<4 (from mlflow)
#9 4.517   Downloading flask-3.1.3-py3-none-any.whl.metadata (3.2 kB)
#9 5.169 Collecting aiohttp<4,>=3.7.0 (from mlflow)
#9 5.270   Downloading aiohttp-3.14.5-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl.metadata (8.3 kB)
#9 5.379 Collecting alembic!=1.10.0,<2 (from mlflow)
#9 5.479   Downloading alembic-1.20.1-py3-none-any.whl.metadata (7.3 kB)
#9 5.481 Requirement already satisfied: cryptography<51,>=43.0.0 in /opt/conda/lib/python3.14/site-packages (from mlflow) (50.0.0)
#9 5.620 Collecting docker<8,>=4.0.0 (from mlflow)
#9 5.720   Downloading docker-7.2.0-py3-none-any.whl.metadata (3.8 kB)
#9 5.829 Collecting graphene<4 (from mlflow)
#9 5.929   Downloading graphene-3.4.3-py2.py3-none-any.whl.metadata (6.9 kB)
#9 6.039 Collecting gunicorn<27 (from mlflow)
#9 6.140   Downloading gunicorn-26.2.0-py3-none-any.whl.metadata (5.5 kB)
#9 6.247 Collecting huey<4,>=2.5.4 (from mlflow)
#9 6.348   Downloading huey-3.5.4-py3-none-any.whl.metadata (5.7 kB)
#9 6.516 Collecting matplotlib<4 (from mlflow)
#9 6.622   Downloading matplotlib-3.11.2-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl.metadata (80 kB)
#9 7.093 Collecting numpy<3 (from mlflow)
#9 7.198   Downloading numpy-2.5.4-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl.metadata (6.6 kB)
#9 7.376 Collecting pandas<4 (from mlflow)
#9 7.479   Downloading pandas-3.1.0-cp314-cp314-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl.metadata (18 kB)
#9 7.629 Collecting pyarrow<26,>=4.0.0 (from mlflow)
#9 7.736   Downloading pyarrow-25.0.1-cp314-cp314-manylinux_2_28_x86_64.whl.metadata (3.0 kB)
#9 7.871 Collecting scikit-learn<2 (from mlflow)
#9 7.983   Downloading scikit_learn-1.9.1-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl.metadata (9.3 kB)
#9 8.192 Collecting scipy<2 (from mlflow)
#9 8.299   Downloading scipy-1.18.1-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl.metadata (62 kB)
#9 8.498 Collecting skops<1 (from mlflow)
#9 8.611   Downloading skops-0.16.0-py3-none-any.whl.metadata (4.3 kB)
#9 8.947 Collecting sqlalchemy<3,>=1.4.0 (from mlflow)
#9 9.047   Downloading sqlalchemy-2.1.6-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl.metadata (9.7 kB)
#9 9.051 Requirement already satisfied: anyio!=4.15.0,<5,>=3.6.2 in /opt/conda/lib/python3.14/site-packages (from mlflow-skinny==3.17.2->mlflow) (4.12.1)
#9 9.158 Collecting cachetools<8,>=5.0.0 (from mlflow-skinny==3.17.2->mlflow)
#9 9.258   Downloading cachetools-7.2.8-py3-none-any.whl.metadata (5.5 kB)
#9 9.259 Requirement already satisfied: click<9,>=7.0 in /opt/conda/lib/python3.14/site-packages (from mlflow-skinny==3.17.2->mlflow) (8.4.1)
#9 9.363 Collecting cloudpickle<4 (from mlflow-skinny==3.17.2->mlflow)
#9 9.464   Downloading cloudpickle-3.1.2-py3-none-any.whl.metadata (7.1 kB)
#9 9.578 Collecting databricks-sdk<1,>=0.20.0 (from mlflow-skinny==3.17.2->mlflow)
#9 9.678   Downloading databricks_sdk-0.160.0-py3-none-any.whl.metadata (44 kB)
#9 9.808 Collecting fastapi<1 (from mlflow-skinny==3.17.2->mlflow)
#9 9.908   Downloading fastapi-0.162.0-py3-none-any.whl.metadata (26 kB)
#9 10.03 Collecting gitpython<4,>=3.1.9 (from mlflow-skinny==3.17.2->mlflow)
#9 10.13   Downloading gitpython-3.2.1-py3-none-any.whl.metadata (13 kB)
#9 10.24 Collecting importlib_metadata!=4.7.0,<10,>=3.7.0 (from mlflow-skinny==3.17.2->mlflow)
#9 10.34   Downloading importlib_metadata-9.1.0-py3-none-any.whl.metadata (4.5 kB)
#9 10.45 Collecting opentelemetry-api<3,>=1.9.0 (from mlflow-skinny==3.17.2->mlflow)
#9 10.55   Downloading opentelemetry_api-1.45.2-py3-none-any.whl.metadata (1.4 kB)
#9 10.66 Collecting opentelemetry-proto<3,>=1.9.0 (from mlflow-skinny==3.17.2->mlflow)
#9 10.76   Downloading opentelemetry_proto-1.45.2-py3-none-any.whl.metadata (2.3 kB)
#9 10.86 Collecting opentelemetry-sdk<3,>=1.9.0 (from mlflow-skinny==3.17.2->mlflow)
#9 10.97   Downloading opentelemetry_sdk-1.45.2-py3-none-any.whl.metadata (1.6 kB)
#9 10.97 Requirement already satisfied: packaging<27 in /opt/conda/lib/python3.14/site-packages (from mlflow-skinny==3.17.2->mlflow) (26.3)
#9 11.15 Collecting protobuf<8,>=3.12.0 (from mlflow-skinny==3.17.2->mlflow)
#9 11.25   Downloading protobuf-7.36.2-cp310-abi3-manylinux2014_x86_64.whl.metadata (595 bytes)
#9 11.26 Requirement already satisfied: pydantic<3,>=2.0.0 in /opt/conda/lib/python3.14/site-packages (from mlflow-skinny==3.17.2->mlflow) (2.13.4)
#9 11.26 Requirement already satisfied: python-dotenv<2,>=0.19.0 in /opt/conda/lib/python3.14/site-packages (from mlflow-skinny==3.17.2->mlflow) (1.2.2)
#9 11.37 Collecting pyyaml<7,>=5.1 (from mlflow-skinny==3.17.2->mlflow)
#9 11.47   Downloading pyyaml-6.0.3-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl.metadata (2.4 kB)
#9 11.48 Requirement already satisfied: requests<3,>=2.17.3 in /opt/conda/lib/python3.14/site-packages (from mlflow-skinny==3.17.2->mlflow) (2.34.2)
#9 11.58 Collecting sqlparse<1,>=0.4.0 (from mlflow-skinny==3.17.2->mlflow)
#9 11.68   Downloading sqlparse-0.6.1-py3-none-any.whl.metadata (6.9 kB)
#9 11.79 Collecting starlette<2 (from mlflow-skinny==3.17.2->mlflow)
#9 11.89   Downloading starlette-1.10.0-py3-none-any.whl.metadata (6.6 kB)
#9 11.89 Requirement already satisfied: typing-extensions<5,>=4.0.0 in /opt/conda/lib/python3.14/site-packages (from mlflow-skinny==3.17.2->mlflow) (4.16.0)
#9 12.00 Collecting uvicorn<1 (from mlflow-skinny==3.17.2->mlflow)
#9 12.10   Downloading uvicorn-0.54.0-py3-none-any.whl.metadata (6.6 kB)
#9 12.21 Collecting aiohappyeyeballs>=2.5.0 (from aiohttp<4,>=3.7.0->mlflow)
#9 12.31   Downloading aiohappyeyeballs-2.7.1-py3-none-any.whl.metadata (5.9 kB)
#9 12.41 Collecting aiosignal>=1.4.0 (from aiohttp<4,>=3.7.0->mlflow)
#9 12.51   Downloading aiosignal-1.4.0-py3-none-any.whl.metadata (3.7 kB)
#9 12.62 Collecting attrs>=17.3.0 (from aiohttp<4,>=3.7.0->mlflow)
#9 12.72   Downloading attrs-26.1.0-py3-none-any.whl.metadata (8.8 kB)
#9 12.85 Collecting frozenlist>=1.1.1 (from aiohttp<4,>=3.7.0->mlflow)
#9 12.95   Downloading frozenlist-1.8.0-cp314-cp314-manylinux1_x86_64.manylinux_2_28_x86_64.manylinux_2_5_x86_64.whl.metadata (20 kB)
#9 13.21 Collecting multidict<8.0,>=4.5 (from aiohttp<4,>=3.7.0->mlflow)
#9 13.31   Downloading multidict-7.2.1-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl.metadata (6.1 kB)
#9 13.44 Collecting propcache>=0.2.0 (from aiohttp<4,>=3.7.0->mlflow)
#9 13.54   Downloading propcache-0.5.4-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl.metadata (25 kB)
#9 13.78 Collecting yarl<2.0,>=1.25.1 (from aiohttp<4,>=3.7.0->mlflow)
#9 13.90   Downloading yarl-1.25.1-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl.metadata (111 kB)
#9 14.20 Collecting Mako (from alembic!=1.10.0,<2->mlflow)
#9 14.30   Downloading mako-1.4.3-py3-none-any.whl.metadata (2.9 kB)
#9 14.30 Requirement already satisfied: idna>=2.8 in /opt/conda/lib/python3.14/site-packages (from anyio!=4.15.0,<5,>=3.6.2->mlflow-skinny==3.17.2->mlflow) (3.18)
#9 14.30 Requirement already satisfied: cffi>=2.0.0 in /opt/conda/lib/python3.14/site-packages (from cryptography<51,>=43.0.0->mlflow) (2.1.1)
#9 14.73 Collecting certifi>=2026.10.19 (from databricks-sdk<1,>=0.20.0->mlflow-skinny==3.17.2->mlflow)
#9 14.83   Downloading certifi-2026.10.23-py3-none-any.whl.metadata (2.5 kB)
#9 14.95 Collecting google-auth~=2.0 (from databricks-sdk<1,>=0.20.0->mlflow-skinny==3.17.2->mlflow)
#9 15.10   Downloading google_auth-2.62.1-py3-none-any.whl.metadata (6.0 kB)
#9 15.13 Requirement already satisfied: urllib3<3,>=1.26 in /opt/conda/lib/python3.14/site-packages (from databricks-sdk<1,>=0.20.0->mlflow-skinny==3.17.2->mlflow) (2.7.0)
#9 15.13 Requirement already satisfied: typing-inspection>=0.4.2 in /opt/conda/lib/python3.14/site-packages (from fastapi<1->mlflow-skinny==3.17.2->mlflow) (0.4.3)
#9 15.13 Requirement already satisfied: annotated-doc>=0.0.2 in /opt/conda/lib/python3.14/site-packages (from fastapi<1->mlflow-skinny==3.17.2->mlflow) (0.0.5)
#9 15.23 Collecting blinker>=1.9.0 (from Flask<4->mlflow)
#9 15.33   Downloading blinker-1.9.0-py3-none-any.whl.metadata (1.6 kB)
#9 15.44 Collecting itsdangerous>=2.2.0 (from Flask<4->mlflow)
#9 15.55   Downloading itsdangerous-2.2.0-py3-none-any.whl.metadata (1.9 kB)
#9 15.55 Requirement already satisfied: jinja2>=3.1.2 in /opt/conda/lib/python3.14/site-packages (from Flask<4->mlflow) (3.1.6)
#9 15.55 Requirement already satisfied: markupsafe>=2.1.1 in /opt/conda/lib/python3.14/site-packages (from Flask<4->mlflow) (3.0.3)
#9 15.65 Collecting werkzeug>=3.1.0 (from Flask<4->mlflow)
#9 15.75   Downloading werkzeug-3.1.9-py3-none-any.whl.metadata (4.1 kB)
#9 15.86 Collecting gitdb<5,>=4.0.1 (from gitpython<4,>=3.1.9->mlflow-skinny==3.17.2->mlflow)
#9 15.96   Downloading gitdb-4.0.12-py3-none-any.whl.metadata (1.2 kB)
#9 16.07 Collecting smmap<6,>=3.0.1 (from gitdb<5,>=4.0.1->gitpython<4,>=3.1.9->mlflow-skinny==3.17.2->mlflow)
#9 16.17   Downloading smmap-5.0.3-py3-none-any.whl.metadata (4.6 kB)
#9 16.28 Collecting pyasn1-modules>=0.2.1 (from google-auth~=2.0->databricks-sdk<1,>=0.20.0->mlflow-skinny==3.17.2->mlflow)
#9 16.38   Downloading pyasn1_modules-0.4.2-py3-none-any.whl.metadata (3.5 kB)
#9 16.49 Collecting graphql-core<3.3,>=3.1 (from graphene<4->mlflow)
#9 16.59   Downloading graphql_core-3.2.13-py3-none-any.whl.metadata (11 kB)
#9 16.70 Collecting graphql-relay<3.3,>=3.1 (from graphene<4->mlflow)
#9 16.80   Downloading graphql_relay-3.2.0-py3-none-any.whl.metadata (12 kB)
#9 16.90 Collecting python-dateutil<3,>=2.7.0 (from graphene<4->mlflow)
#9 17.00   Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl.metadata (8.4 kB)
#9 17.11 Collecting zipp>=3.20 (from importlib_metadata!=4.7.0,<10,>=3.7.0->mlflow-skinny==3.17.2->mlflow)
#9 17.21   Downloading zipp-4.1.2-py3-none-any.whl.metadata (3.6 kB)
#9 17.35 Collecting contourpy>=1.0.1 (from matplotlib<4->mlflow)
#9 17.46   Downloading contourpy-1.4.0-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl.metadata (3.8 kB)
#9 17.57 Collecting cycler>=0.10 (from matplotlib<4->mlflow)
#9 17.67   Downloading cycler-0.12.1-py3-none-any.whl.metadata (3.8 kB)
#9 17.97 Collecting fonttools>=4.28.2 (from matplotlib<4->mlflow)
#9 18.07   Downloading fonttools-4.68.0-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.whl.metadata (139 kB)
#9 18.39 Collecting kiwisolver>=1.3.1 (from matplotlib<4->mlflow)
#9 18.49   Downloading kiwisolver-1.5.1-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.whl.metadata (5.2 kB)
#9 18.78 Collecting pillow>=9 (from matplotlib<4->mlflow)
#9 18.88   Downloading pillow-13.0.0-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl.metadata (9.1 kB)
#9 18.99 Collecting pyparsing>=3 (from matplotlib<4->mlflow)
#9 19.09   Downloading pyparsing-3.3.3-py3-none-any.whl.metadata (5.9 kB)
#9 19.20 Collecting opentelemetry-semantic-conventions==0.66b2 (from opentelemetry-sdk<3,>=1.9.0->mlflow-skinny==3.17.2->mlflow)
#9 19.30   Downloading opentelemetry_semantic_conventions-0.66b2-py3-none-any.whl.metadata (2.4 kB)
#9 19.31 Requirement already satisfied: annotated-types>=0.6.0 in /opt/conda/lib/python3.14/site-packages (from pydantic<3,>=2.0.0->mlflow-skinny==3.17.2->mlflow) (0.7.0)
#9 19.31 Requirement already satisfied: pydantic-core==2.46.4 in /opt/conda/lib/python3.14/site-packages (from pydantic<3,>=2.0.0->mlflow-skinny==3.17.2->mlflow) (2.46.4)
#9 19.41 Collecting six>=1.5 (from python-dateutil<3,>=2.7.0->graphene<4->mlflow)
#9 19.51   Downloading six-1.17.0-py2.py3-none-any.whl.metadata (1.7 kB)
#9 19.52 Requirement already satisfied: charset_normalizer<4,>=2 in /opt/conda/lib/python3.14/site-packages (from requests<3,>=2.17.3->mlflow-skinny==3.17.2->mlflow) (3.4.7)
#9 19.63 Collecting joblib>=1.4.0 (from scikit-learn<2->mlflow)
#9 19.73   Downloading joblib-1.6.0-py3-none-any.whl.metadata (6.5 kB)
#9 19.85 Collecting narwhals>=2.0.1 (from scikit-learn<2->mlflow)
#9 19.95   Downloading narwhals-2.28.0-py3-none-any.whl.metadata (15 kB)
#9 20.06 Collecting threadpoolctl>=3.5.0 (from scikit-learn<2->mlflow)
#9 20.16   Downloading threadpoolctl-3.7.0-py3-none-any.whl.metadata (24 kB)
#9 20.27 Collecting prettytable>=3.9 (from skops<1->mlflow)
#9 20.37   Downloading prettytable-3.18.0-py3-none-any.whl.metadata (37 kB)
#9 20.38 Requirement already satisfied: h11>=0.8 in /opt/conda/lib/python3.14/site-packages (from uvicorn<1->mlflow-skinny==3.17.2->mlflow) (0.16.0)
#9 20.67 Collecting botocore<1.44.0,>=1.43.123 (from boto3)
#9 20.77   Downloading botocore-1.43.123-py3-none-any.whl.metadata (5.6 kB)
#9 20.87 Collecting jmespath<2.0.0,>=0.7.1 (from boto3)
#9 20.98   Downloading jmespath-1.1.0-py3-none-any.whl.metadata (7.6 kB)
#9 21.08 Collecting s3transfer<0.20.0,>=0.19.0 (from boto3)
#9 21.18   Downloading s3transfer-0.19.3-py3-none-any.whl.metadata (1.7 kB)
#9 21.20 Requirement already satisfied: pycparser in /opt/conda/lib/python3.14/site-packages (from cffi>=2.0.0->cryptography<51,>=43.0.0->mlflow) (3.0)
#9 21.31 Collecting wcwidth>=0.3.5 (from prettytable>=3.9->skops<1->mlflow)
#9 21.41   Downloading wcwidth-0.9.4-cp310-abi3-manylinux2014_x86_64.manylinux_2_17_x86_64.whl.metadata (23 kB)
#9 21.53 Collecting pyasn1<0.7.0,>=0.6.1 (from pyasn1-modules>=0.2.1->google-auth~=2.0->databricks-sdk<1,>=0.20.0->mlflow-skinny==3.17.2->mlflow)
#9 21.63   Downloading pyasn1-0.6.5-py3-none-any.whl.metadata (8.4 kB)
#9 21.74 Downloading mlflow-3.17.2-py3-none-any.whl (12.0 MB)
#9 24.39    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12.0/12.0 MB 4.8 MB/s  0:00:02
#9 24.49 Downloading mlflow_skinny-3.17.2-py3-none-any.whl (4.1 MB)
#9 24.82    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.1/4.1 MB 12.2 MB/s  0:00:00
#9 24.92 Downloading mlflow_tracing-3.17.2-py3-none-any.whl (2.0 MB)
#9 25.18    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.0/2.0 MB 7.3 MB/s  0:00:00
#9 25.28 Downloading aiohttp-3.14.5-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl (1.9 MB)
#9 25.53    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.9/1.9 MB 7.9 MB/s  0:00:00
#9 25.63 Downloading alembic-1.20.1-py3-none-any.whl (270 kB)
#9 25.76 Downloading cachetools-7.2.8-py3-none-any.whl (19 kB)
#9 25.86 Downloading cloudpickle-3.1.2-py3-none-any.whl (22 kB)
#9 25.97 Downloading databricks_sdk-0.160.0-py3-none-any.whl (1.2 MB)
#9 26.07    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.2/1.2 MB 11.2 MB/s  0:00:00
#9 26.17 Downloading docker-7.2.0-py3-none-any.whl (148 kB)
#9 26.28 Downloading fastapi-0.162.0-py3-none-any.whl (148 kB)
#9 26.40 Downloading flask-3.1.3-py3-none-any.whl (103 kB)
#9 26.51 Downloading flask_cors-6.0.5-py3-none-any.whl (16 kB)
#9 26.61 Downloading gitpython-3.2.1-py3-none-any.whl (231 kB)
#9 26.73 Downloading gitdb-4.0.12-py3-none-any.whl (62 kB)
#9 26.83 Downloading google_auth-2.62.1-py3-none-any.whl (267 kB)
#9 26.95 Downloading graphene-3.4.3-py2.py3-none-any.whl (114 kB)
#9 27.06 Downloading graphql_core-3.2.13-py3-none-any.whl (268 kB)
#9 27.18 Downloading graphql_relay-3.2.0-py3-none-any.whl (16 kB)
#9 27.28 Downloading gunicorn-26.2.0-py3-none-any.whl (228 kB)
#9 27.40 Downloading huey-3.5.4-py3-none-any.whl (135 kB)
#9 27.51 Downloading importlib_metadata-9.1.0-py3-none-any.whl (28 kB)
#9 27.62 Downloading matplotlib-3.11.2-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl (11.0 MB)
#9 28.81    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 11.0/11.0 MB 9.1 MB/s  0:00:01
#9 28.92 Downloading multidict-7.2.1-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl (506 kB)
#9 29.69 Downloading numpy-2.5.4-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl (16.7 MB)
#9 30.70    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 16.7/16.7 MB 16.7 MB/s  0:00:01
#9 30.80 Downloading opentelemetry_api-1.45.2-py3-none-any.whl (60 kB)
#9 30.90 Downloading opentelemetry_proto-1.45.2-py3-none-any.whl (72 kB)
#9 31.01 Downloading opentelemetry_sdk-1.45.2-py3-none-any.whl (141 kB)
#9 31.11 Downloading opentelemetry_semantic_conventions-0.66b2-py3-none-any.whl (206 kB)
#9 31.24 Downloading pandas-3.1.0-cp314-cp314-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl (12.0 MB)
#9 31.88    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12.0/12.0 MB 18.7 MB/s  0:00:00
#9 31.98 Downloading protobuf-7.36.2-cp310-abi3-manylinux2014_x86_64.whl (343 kB)
#9 32.10 Downloading pyarrow-25.0.1-cp314-cp314-manylinux_2_28_x86_64.whl (50.1 MB)
#9 35.63    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 50.1/50.1 MB 14.2 MB/s  0:00:03
#9 35.73 Downloading python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
#9 35.85 Downloading pyyaml-6.0.3-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl (794 kB)
#9 35.90    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 794.2/794.2 kB 15.3 MB/s  0:00:00
#9 36.00 Downloading scikit_learn-1.9.1-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl (9.2 MB)
#9 36.61    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 9.2/9.2 MB 15.0 MB/s  0:00:00
#9 36.71 Downloading scipy-1.18.1-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl (35.3 MB)
#9 40.07    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 35.3/35.3 MB 10.5 MB/s  0:00:03
#9 40.17 Downloading skops-0.16.0-py3-none-any.whl (148 kB)
#9 40.29 Downloading smmap-5.0.3-py3-none-any.whl (24 kB)
#9 40.41 Downloading sqlalchemy-2.1.6-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl (4.6 MB)
#9 41.00    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.6/4.6 MB 7.7 MB/s  0:00:00
#9 41.11 Downloading sqlparse-0.6.1-py3-none-any.whl (51 kB)
#9 41.21 Downloading starlette-1.10.0-py3-none-any.whl (80 kB)
#9 41.32 Downloading uvicorn-0.54.0-py3-none-any.whl (87 kB)
#9 41.42 Downloading yarl-1.25.1-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl (117 kB)
#9 41.53 Downloading boto3-1.43.123-py3-none-any.whl (140 kB)
#9 41.64 Downloading botocore-1.43.123-py3-none-any.whl (16.2 MB)
#9 44.63    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 16.2/16.2 MB 5.4 MB/s  0:00:02
#9 44.73 Downloading jmespath-1.1.0-py3-none-any.whl (20 kB)
#9 44.83 Downloading s3transfer-0.19.3-py3-none-any.whl (90 kB)
#9 44.94 Downloading pymysql-1.2.3-py3-none-any.whl (46 kB)
#9 45.04 Downloading aiohappyeyeballs-2.7.1-py3-none-any.whl (15 kB)
#9 45.15 Downloading aiosignal-1.4.0-py3-none-any.whl (7.5 kB)
#9 45.25 Downloading attrs-26.1.0-py3-none-any.whl (67 kB)
#9 45.36 Downloading blinker-1.9.0-py3-none-any.whl (8.5 kB)
#9 45.46 Downloading certifi-2026.10.23-py3-none-any.whl (135 kB)
#9 45.57 Downloading contourpy-1.4.0-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl (384 kB)
#9 45.72 Downloading cycler-0.12.1-py3-none-any.whl (8.3 kB)
#9 45.86 Downloading fonttools-4.68.0-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (5.4 MB)
#9 46.35    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5.4/5.4 MB 11.2 MB/s  0:00:00
#9 46.46 Downloading frozenlist-1.8.0-cp314-cp314-manylinux1_x86_64.manylinux_2_28_x86_64.manylinux_2_5_x86_64.whl (231 kB)
#9 46.58 Downloading itsdangerous-2.2.0-py3-none-any.whl (16 kB)
#9 46.68 Downloading joblib-1.6.0-py3-none-any.whl (306 kB)
#9 46.80 Downloading kiwisolver-1.5.1-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (1.5 MB)
#9 46.89    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.5/1.5 MB 15.9 MB/s  0:00:00
#9 46.99 Downloading narwhals-2.28.0-py3-none-any.whl (490 kB)
#9 47.12 Downloading pillow-13.0.0-cp314-cp314-manylinux_2_27_x86_64.manylinux_2_28_x86_64.whl (7.1 MB)
#9 47.58    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 7.1/7.1 MB 15.4 MB/s  0:00:00
#9 47.68 Downloading prettytable-3.18.0-py3-none-any.whl (37 kB)
#9 47.79 Downloading propcache-0.5.4-cp314-cp314-manylinux2014_x86_64.manylinux_2_17_x86_64.manylinux_2_28_x86_64.whl (232 kB)
#9 47.90 Downloading pyasn1_modules-0.4.2-py3-none-any.whl (181 kB)
#9 48.01 Downloading pyasn1-0.6.5-py3-none-any.whl (84 kB)
#9 48.11 Downloading pyparsing-3.3.3-py3-none-any.whl (126 kB)
#9 48.23 Downloading six-1.17.0-py2.py3-none-any.whl (11 kB)
#9 48.33 Downloading threadpoolctl-3.7.0-py3-none-any.whl (26 kB)
#9 48.44 Downloading wcwidth-0.9.4-cp310-abi3-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (785 kB)
#9 48.49    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 785.9/785.9 kB 36.5 MB/s  0:00:00
#9 48.59 Downloading werkzeug-3.1.9-py3-none-any.whl (228 kB)
#9 48.71 Downloading zipp-4.1.2-py3-none-any.whl (10 kB)
#9 48.86 Downloading mako-1.4.3-py3-none-any.whl (80 kB)
#9 49.27 Installing collected packages: huey, zipp, werkzeug, wcwidth, uvicorn, threadpoolctl, sqlparse, sqlalchemy, smmap, six, pyyaml, pyparsing, pymysql, pyasn1, pyarrow, protobuf, propcache, pillow, opentelemetry-api, numpy, narwhals, multidict, Mako, kiwisolver, jmespath, itsdangerous, gunicorn, graphql-core, frozenlist, fonttools, cycler, cloudpickle, certifi, cachetools, blinker, attrs, aiohappyeyeballs, yarl, starlette, scipy, python-dateutil, pyasn1-modules, prettytable, opentelemetry-semantic-conventions, opentelemetry-proto, joblib, importlib_metadata, graphql-relay, gitdb, Flask, contourpy, alembic, aiosignal, scikit-learn, pandas, opentelemetry-sdk, matplotlib, graphene, google-auth, gitpython, Flask-CORS, fastapi, docker, botocore, aiohttp, skops, s3transfer, databricks-sdk, mlflow-tracing, mlflow-skinny, boto3, mlflow
#9 55.25   Attempting uninstall: certifi
#9 55.26     Found existing installation: certifi 2026.7.22
#9 55.26     Uninstalling certifi-2026.7.22:
#9 55.27       Successfully uninstalled certifi-2026.7.22
#9 73.30 
#9 73.31 Successfully installed Flask-3.1.3 Flask-CORS-6.0.5 Mako-1.4.3 aiohappyeyeballs-2.7.1 aiohttp-3.14.5 aiosignal-1.4.0 alembic-1.20.1 attrs-26.1.0 blinker-1.9.0 boto3-1.43.123 botocore-1.43.123 cachetools-7.2.8 certifi-2026.10.23 cloudpickle-3.1.2 contourpy-1.4.0 cycler-0.12.1 databricks-sdk-0.160.0 docker-7.2.0 fastapi-0.162.0 fonttools-4.68.0 frozenlist-1.8.0 gitdb-4.0.12 gitpython-3.2.1 google-auth-2.62.1 graphene-3.4.3 graphql-core-3.2.13 graphql-relay-3.2.0 gunicorn-26.2.0 huey-3.5.4 importlib_metadata-9.1.0 itsdangerous-2.2.0 jmespath-1.1.0 joblib-1.6.0 kiwisolver-1.5.1 matplotlib-3.11.2 mlflow-3.17.2 mlflow-skinny-3.17.2 mlflow-tracing-3.17.2 multidict-7.2.1 narwhals-2.28.0 numpy-2.5.4 opentelemetry-api-1.45.2 opentelemetry-proto-1.45.2 opentelemetry-sdk-1.45.2 opentelemetry-semantic-conventions-0.66b2 pandas-3.1.0 pillow-13.0.0 prettytable-3.18.0 propcache-0.5.4 protobuf-7.36.2 pyarrow-25.0.1 pyasn1-0.6.5 pyasn1-modules-0.4.2 pymysql-1.2.3 pyparsing-3.3.3 python-dateutil-2.9.0.post0 pyyaml-6.0.3 s3transfer-0.19.3 scikit-learn-1.9.1 scipy-1.18.1 six-1.17.0 skops-0.16.0 smmap-5.0.3 sqlalchemy-2.1.6 sqlparse-0.6.1 starlette-1.10.0 threadpoolctl-3.7.0 uvicorn-0.54.0 wcwidth-0.9.4 werkzeug-3.1.9 yarl-1.25.1 zipp-4.1.2
#9 73.31 WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager, possibly rendering your system unusable. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv. Use the --root-user-action option if you know what you are doing and want to suppress this warning.
#9 DONE 75.7s

#10 exporting to image
#10 exporting layers
#10 exporting layers 20.3s done
#10 exporting manifest sha256:727d9a53d8ff86bc3d4349984af1baab28cad4f16bab4732d796468c7a2239f3 0.0s done
#10 exporting config sha256:d8ebdf08f0031aa53397f116eed7a7129fa94d413fc1b69e94b868e89577bdd9 0.0s done
#10 exporting attestation manifest sha256:b5e530c5b00ac71ea6c9b768b97e9a7b31ef9c9cffcc01580cdb61fd18eab99b 0.0s done
#10 exporting manifest list sha256:ba6040fb81d281ddf4f425b61a8cac0043657f5222f3bcfb433c7e8f1b528025 0.0s done
#10 naming to docker.io/library/netology-ml:netology-ml done
#10 unpacking to docker.io/library/netology-ml:netology-ml
#10 unpacking to docker.io/library/netology-ml:netology-ml 16.3s done
#10 DONE 36.7s

View build details: docker-desktop://dashboard/build/desktop-linux/desktop-linux/7450sjuztwju1z19amubu8gek
```

Результат запуска `docker run`:

```
Hello Netology
```
