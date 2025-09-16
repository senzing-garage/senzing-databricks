# senzing-databricks

Senzing integration in Databricks Spark workflows.


## Tutorial components

This repository contains two Jupyter notebooks which demonstrate
[Senzing](https://senzing.com/) _entity resolution_ integrated
with [Apache Spark](https://spark.apache.org/) from Databricks:

**`spark_quickstart.ipynb`**:

An introductory tutorial showing how to integrate Senzing with
[Spark DataFrames](https://spark.apache.org/docs/4.0.0/sql-programming-guide.html#datasets-and-dataframes)
for running entity resolution in a batch mode. This covers loading
multiple datasets, configuring Senzing, processing records, and
enriching DataFrames with entity resolution results.

**`spark_streaming.ipynb`**:
Demonstrates real-time entity resolution using
[Spark Structured Streaming](https://spark.apache.org/docs/4.0.0/streaming/getting-started.html).
This shows how to process streaming data through Spark and send 
[PII features](https://en.wikipedia.org/wiki/Personal_data)
to Senzing for continuous entity resolution, simulating a real-time
data processing pipeline.

Both tutorials require a Docker container running for the Senzing gRPC
server whenever you run the Jupyter notebooks:

  * <https://github.com/senzing-garage/serve-grpc>
  * <https://hub.docker.com/r/senzing/serve-grpc>

Start with the `spark_quickstart.ipynb` tutorial for detailed
explanations of the core concepts.


## Requirements

These tutorials were developed on MacOS, though they should run fine
on Linux as well.

Platform requirements are:

  * Python 3.13
  * Spark requires Java 17 or 21

You can find more details about the [Java](https://www.java.com/)
requirements in the
[Apache Spark documentation](https://spark.apache.org/docs/latest/).

To set up the Python environment:

```bash
python3 -m venv venv
source venv/bin/activate

python3 -m pip install -U pip wheel
python3 -m pip install -r requirements.txt
```

Alternatively use the `requirements.txt` file with
[`uv`](https://docs.astral.sh/uv/),
[`poetry`](https://python-poetry.org/docs/),
or your favorite Python dependency manager.

You also need to pull the latest Docker container for Senzing:

```bash
docker pull senzing/serve-grpc:latest
```

Then launch this container and have it running in the background:

```bash
docker run -it --publish 8261:8261 --rm senzing/serve-grpc
```

Then launch Jupyter to run the notebooks:

```bash
./venv/bin/jupyter-lab
```


## Troubleshooting

Be aware that running `pip install senzing` without specifying a
version number will not give you the correct version. Make sure to
use the versions specified in the `requirements.txt` file.

If you experience gRPC errors, these may be due to an outdated
Docker container.
