# senzing-databricks
Senzing integration in Databricks Spark workflows

## Requirements

Install the required Python modules with `pip install -r requirements.txt` (or use `uv` if you prefer).

Spark requires Java 17 or 21. You can find more details in [the Apache Spark documentation](https://spark.apache.org/docs/latest/).

## Troubleshooting

If you are experiencing gRPC errors, this may be due to an outdated Docker container. Use `docker pull senzing/serve-grpc:latest` to update it.

Be aware that running `pip install senzing` without specifying a version number will not give you the correct version - make sure to use the versions specified in the `requirements.txt` file.
