# MITOS-Container
Instructions to use MITOS mitochondrial genome annotater as a Docker container for use on local machines

MITOS & MITOS 2 currently use a number of depreciated dependencies that make it difficult to install using Bioconda. I Below is the quickest and easiest way I have found to get started with MITOS on a local machine. 

In the future, I plan to upload scripts to batch process through mitogenomes. 

### Links to MITOS
- [GitLab page](https://gitlab.com/Bernt/MITOS/-/tree/master/)
- [Bioconda page](https://bioconda.github.io/recipes/mitos/README.html?highlight=mitos#package-package%20&#x27;mitos&#x27;)
- [Reference Databases](https://zenodo.org/record/4284483#.ZBIvsUfMKX0)
- [Docker images](https://quay.io/repository/biocontainers/mitos?tab=tags) 

### Instructions

1. Install the latest version of [Docker Desktop](https://www.docker.com/products/docker-desktop/) for your prefered operating system
2. Visit the Docker image link above and note the MITOS version you want to use. Replace the `<tag>` below with the verion number. This will create a Docker image that you can view in the Docker Desktop app.
    - `docker pull quay.io/biocontainers/mitos:<tag>`
    - Ex: `docker pull quay.io/biocontainers/mitos:2.1.3--pyhdfd78af_0`
3. Adapt the command below to run your containerCreate container

