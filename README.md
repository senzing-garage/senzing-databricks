# senzing-databricks
Senzing integration in Databricks Spark workflows.

## Files in this repository

This repository contains two Jupyter notebooks demonstrating [Senzing](https://senzing.com/) entity resolution with Apache Spark/Databricks:

- **`spark_quickstart.ipynb`** - A comprehensive tutorial showing how to integrate Senzing with Spark DataFrames for batch entity resolution. Covers loading multiple datasets, configuring Senzing, processing records, and enriching DataFrames with entity resolution results.

- **`spark_streaming.ipynb`** - Demonstrates real-time entity resolution using Spark Structured Streaming. Shows how to process streaming data through Spark and send it to Senzing for continuous entity resolution, simulating a real-time data processing pipeline.

Both tutorials use demo data and require a [Senzing gRPC server](https://github.com/senzing-garage/serve-grpc) running in Docker. Start with the quickstart tutorial for detailed explanations of the core concepts.

## Requirements

These tutorials were developed on MacOS with Python 3.13.

Install the required Python modules with `pip install -r requirements.txt` (or use `uv` if you prefer).

Spark requires Java 17 or 21. You can find more details in [the Apache Spark documentation](https://spark.apache.org/docs/latest/).

## Troubleshooting

If you are experiencing gRPC errors, this may be due to an outdated Docker container. Use `docker pull senzing/serve-grpc:latest` to update it.

Be aware that running `pip install senzing` without specifying a version number will not give you the correct version - make sure to use the versions specified in the `requirements.txt` file.
