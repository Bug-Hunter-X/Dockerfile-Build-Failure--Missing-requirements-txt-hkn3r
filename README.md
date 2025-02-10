# Dockerfile Bug: Missing requirements.txt
This repository demonstrates a common error in Dockerfiles: attempting to use a requirements file before it's been copied into the image.

## Bug
The original `Dockerfile` attempts to install packages listed in `requirements.txt` before the file is copied into the image's context. This results in a build failure.

## Solution
The `DockerfileFixed` demonstrates the correct order: copy `requirements.txt` *before* running `pip install`.

## How to reproduce
1. Clone this repository.
2. Attempt to build the original `Dockerfile` using `docker build -t my-app .`
3. Observe the build failure.
4. Build the `DockerfileFixed` using `docker build -t my-app-fixed .`
5. Observe successful build.
