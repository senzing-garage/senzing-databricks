# senzing-databricks

Senzing integration in Databricks Spark workflows.


## Files in this repository

This repository contains two Jupyter notebooks demonstrating
[Senzing](https://senzing.com/) _entity resolution_ integrated
with Apache Spark / Databricks:

**`spark_quickstart.ipynb`**:
A comprehensive tutorial showing how to integrate Senzing with Spark
DataFrames for batch entity resolution. Covers loading multiple
datasets, configuring Senzing, processing records, and enriching
DataFrames with entity resolution results.

**`spark_streaming.ipynb`**:
Demonstrates real-time entity resolution using Spark Structured
Streaming. Shows how to process streaming data through Spark and send
it to Senzing for continuous entity resolution, simulating a real-time
data processing pipeline.

Both tutorials require having a Docker container running for the
[Senzing gRPC server](https://github.com/senzing-garage/serve-grpc)
whenever you run the Jupyter notebooks.

Start with the `spark_quickstart.ipynb` tutorial for detailed
explanations of the core concepts.


## Requirements

These tutorials were developed on MacOS, though they should run fine
on Linux as well.

Platform requirements are:

  * Python 3.13
  * Spark requires Java 17 or 21

You can find more details about the Java requirements in
[the Apache Spark documentation](https://spark.apache.org/docs/latest/).

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

Also, pull the latest Docker container for Senzing:

```bash
docker pull senzing/serve-grpc:latest
```

And then launch this container and keep it running in the background:

```bash
docker run -it --publish 8261:8261 --rm senzing/serve-grpc
```

Then launch Jupyter and run the notebooks:

```bash
./venv/bin/jupyter-lab
```


## Troubleshooting

If you are experiencing gRPC errors, this may be due to an outdated
Docker container.

Be aware that running `pip install senzing` without specifying a
version number will not give you the correct version. Make sure to
use the versions specified in the `requirements.txt` file.
