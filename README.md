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
2. Visit the Docker image link above and note the MITOS version you want to use. When running this in the CLI, replace the `<tag>` below with the verion number. This will create a Docker image that you can view in the Docker Desktop app.
    - `$ docker pull quay.io/biocontainers/mitos:<tag>`
    - Ex: `$ docker pull quay.io/biocontainers/mitos:2.1.3--pyhdfd78af_0`
3. Adapt the command below to create and run a container from the above image.
    ```
    $ docker run \
    --name mitos2.1.3 \
    -it \
    -v /Users/person/mydata:/mnt/mydata \
    -w /mnt/mydata \
    imageID
    ```
    - `--name` names the container
    - `-it` runs the container in interactive mode
    - `-v` mounts and binds a local directory (`/Users/person/mydata`) to the container (`/mnt/mydata`)
    - `-w` sets the working directory of the interactive session to the specified path (`/mnt/mydata`)
    - `imageID` is a placeholder value where the user will enter in the hash value given to the image by Docker. Image ID marked in red below:
        <img src="img/imgID.png" alt="screenshot of Images tab in Docker Desktop"/>
4. From the interactive terminal run the following code to check that the container started properly:
    - `$ runmitos.py --version`
        - This will check to see MITOS is working properly by outputing the version number of the software  
    - `$ pwd`
        - This will print the working directory and should point you to the path specifed in `-w`
    - `$ ls`
        - This will list the contents of the local directory you bound to this container

