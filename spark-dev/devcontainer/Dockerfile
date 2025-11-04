# Use a Python base image (Debian-based)
FROM python:3.10-slim-bullseye

# Install OpenJDK 17 (Java is still required to run Spark's JVM components)
RUN apt-get update && \
    apt-get install -y --no-install-recommends openjdk-17-jre wget && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Set Java Home environment variable
ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64

# Install PySpark (this also brings Spark binaries)
RUN pip install --no-cache-dir pyspark==3.5.0

# 👇 THE CORRECTION IS HERE 👇
# Find the actual directory containing the Spark binaries installed by pip (usually ends in /pyspark/)
# Then append the 'bin' path to SPARK_HOME for correct functionality.
RUN SPARK_PYTHON_PATH=$(python -c "import pyspark; print(pyspark.__file__)" | sed 's/__init__.py$//') && \
    echo "export SPARK_HOME=$SPARK_PYTHON_PATH" >> /etc/bash.bashrc && \
    echo "export PATH=\$PATH:\$SPARK_HOME/bin" >> /etc/bash.bashrc

# Set a working directory for your project
WORKDIR /workspace