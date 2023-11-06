# open-reproducible-app-package

This repository supports the BiDS23 satellite event: 

**Open & Reproducible workflows in Earth Observation (OREO)****

__Many cloud-based solutions for workflows in EO are available to users today, but only few support reproducibility or comply with FAIR data principles. In this tutorial we will demonstrate three solutions that meet these requirements: openEO process graphs, OGC Best Practice for EO Application Package and Deep ESDL workflows. Participants will be able to follow along using Jupyter lab notebooks, get familiarized with basic concepts and exemplify reproducibility for a set of use cases using workflows based on all three approaches. Users will also learn first-hand how these approaches are used in practice to build capacity on EO Open Data Science in the cloud (in the context of ESA’s Cubes and Clouds MOOC) and to enable reproducibility of algorithms feeding the NASA-ESA-JAXA EO Dashboard.__

Instructors: 

* Anca Anghelea (ESA)
* Claudio Iacopino (ESA)
* Patrick Griffiths (ESA)

## Application Package reproducibility

### Personas

* **Alice** developed a Water Body detection Earth Observation application and package it as an EO Application Package
* **Bob** scripts the execution of application

### Scenario

Alice included in the water bodies detection Application Package software repository a Continuous Integration configuration relying on Github Actions to:

* build the containers
* push the built containers to Github container registry
* update the Application Package with these new container references
* push the updated Application Package to Github's artifact registry

Alice sent an email to Bob:

<hr>
from: alice@acme.io

to: bob@acme.io

subject: Detecting water bodies with NDWI and the Otsu threshold


Hi Bob!

checkout my new application package for detecting water bodies using NDWI and the Ostu threshold.

I've ran it over our test site bounding box and prelimanry result look promising.

The github repo is https://github.com/Terradue/app-package-training-bids23 and I've just released version 1.0.0.

Let me know!

Cheers

Alice
<hr>

With this information, Bob scripts the Application Execution in a Jupyter Notebook.

His environment has a container engine (e.g. podman or docker) and the `cwltool` CWL runner.

## Setting-up the environment on the AppHub Coder application

Clone this repo:

```
git clone https://github.com/Terradue/open-reproducible-app-package.git
```

Click on `File` then `Open Folder...` and type `/workspace/open-reproducible-app-package/`

Go back to the terminal and create the Python environment with:

```
python -m venv env_reproducible_app
source env_reproducible_app/bin/activate
pip install -r requirements.txt
```
