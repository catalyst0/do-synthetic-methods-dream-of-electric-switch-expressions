# Do synthetic methods dream of electric switch expressions
Slides for DevoxxFR 2020

## Content

0. [toward_pattern_matching.ipynb](slideshow/chapter01-toward_pattern_matching.ipynb)
1. [switch_expression.ipynb](slideshow/chapter02-switch_expression.ipynb)
2. [record.ipynb](slideshow/chapter03-record.ipynb)
3. [instanceof.ipynb](slideshow/chapter04-instanceof.ipynb)
4. [sealed_types.ipynb](slideshow/chapter05-sealed_types.ipynb)
5. [helpful_nullpointerexception.ipynb](slideshow/chapter06-helpful_nullpointerexception.ipynb)
6. [foreign_memory_api.ipynb](slideshow/chapter07-foreign_memory_api.ipynb)
7. [text-block.ipynb](slideshow/chapter08-text-block.ipynb)


## Using Jupyter notebook with RISE

### on the cloud
You can see the slides directly in your browser
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/forax/do-synthetic-methods-dream-of-electric-switch-expressions/master)


### or using docker
You need to have docker already installed, then

- get the docker image from dockerhub
  ```
    docker pull forax/do-synthetic-methods-dream-of-electric-switch-expressions
  ```
- run the docker image in a container
  ```
    docker run -p 8888:8888 forax/do-synthetic-methods-dream-of-electric-switch-expressions
  ```
 - open your browser using the `tokenId` printed on the console
   ```
     firefox http://localhost:8888/?token=tokenId
   ```


### or install everything on your laptop
You need to have python3 and latest Java 15 already installed, then

- clone this repository
  ```
    git clone http://github.com/forax/do-synthetic-methods-dream-of-electric-switch-expressions
    cd do-synthetic-methods-dream-of-electric-switch-expressions
  ```
- install [jupyter](https://jupyter.org/install) and [RISE](https://github.com/damianavila/RISE)
  ```
    pip3 install notebook RISE
  ```

- install the [ijava 1.3.0](https://github.com/SpencerPark/IJava) kernel (from Spencer Park)
  ```
  wget https://github.com/SpencerPark/IJava/releases/download/v1.3.0/ijava-1.3.0.zip
  python3 install.py --sys-prefix
  ```
- patch it with the repository file `kernel.json`
  list all kernels to see if the java kernel is installed
  ```
  jupyter kernelspec list
  ```
  then copy the file `kernel.json` in the folder `docker` to the java kernel directory
  ```
  cp docker/kernel.json /path/to/jupyter/kernels/java
  ```
- set the env compiler option enabling the preview features
  ```
  export IJAVA_COMPILER_OPTS="--enable-preview -source 15 --add-modules jdk.incubator.foreign"
  ```
- run the notebook
  ```
  cd jupyter
  jupyter notebook
  ```


### Build jupyter slideshow from jshell files
The jupyter files (.ipynb) are generated from the jshell files using a small Java script.

Using java 15
```
  java --enable-preview build/build.java
```
