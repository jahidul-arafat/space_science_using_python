# Take the basic image from python:3.9-buster
FROM python:3.9-buster

# Give your remote container some labels i.e. "description" and "version"
LABEL description="Remote Container Test"
LABEL version="1.0"

# Copy the requirements.txt file into the Remote Container ./ dir.
# The requirements.txt file will install the following python packages
# numpy, scipy, matplotlib, jupyterlab
COPY requirements.txt ./

# Upgrade the PIP to latest version and then using pip install the packages in requirements.txt
RUN pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt

# Set you PYTHONPATH and WORKDIR
ENV PYTHONPATH "/"
WORKDIR .