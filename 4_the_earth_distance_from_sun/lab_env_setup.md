# Lab Setup in VSCode using Remote Container and VSCode Extensions
## Project: Earth to Sun Distance Calc:: Astronomical Unit
### Step-1: Listing required Packages 
```bash
# Create a requirements.txt file will includes all the necessary packages our remote container should have
> vim requirements.txt
---
# SPICE
spiceypy

# Interactive Shell
ipython
ipywidgets
tqdm

# Jupyterlab
jupyterlab

# Numerics and Science
numpy
pandas
scipy
pingouin

# Plotting
matplotlib
imageio

# Rendering, GUI
visvis

# Machine Learning
scikit-learn
# tensorflow
# keras-tuner

---

```

### Step-2: Creating Dockerfile
```bash
> vim Dockerfile
---
# Get a Pyhton image
FROM python:3.9-buster

# Set some meta information
LABEL description="Remote Container for Space Science using Python"
LABEL version="1.0"

# Copy only the requirements.txt (used for pip install)
COPY requirements.txt ./

# Install all requirements
RUN pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt

# Set the Pythonpath and working directory
ENV PYTHONPATH "/"
WORKDIR .
---
```

### Step-3: Install the `remote-containers` Extension in VSCode
- [x] Once, `remote-containers` extension is installed, 
- [x] Press `SHIFT+CMD+P` and type `>remote-containers: Open Folder in Container`
- [x] This will setup the Docker Container using VSCode extension `remote-containers`
- [x] However, if you already have setup the container and simply wants to reload , press SHIFT+CMD+P and then type `>remote-containers: Rebuild and reopen container`

### Step-4: After container is successfully make it to `live`, look for the following file:`.devcontainer/devcontainer.json`

### Step-5: From the VSCode extension, install `Jupyter` and then `Add to devcontainer.json`. 

---
## Note
`devcontainer.json` is important when someone clone your git repo and try to reproduce the Docker Container or QA team who is planning to test your code, with this `devcontainer.json` they can create the exact same environment.

---

