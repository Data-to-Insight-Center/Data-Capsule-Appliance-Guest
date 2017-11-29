# Data Capsule Appliance Guest VM Creation

This project contains the artifacts to generate a Data Capsule(DC) using Packer (https://www.packer.io/). 

## Getting Started

Let's create a DC image based on Ubuntu 16.04 LTS using Packer.

### Prerequisites

Download the latest version of Packer from https://www.packer.io/downloads.html. A previous version for linux is included in this repo by default. 

### Running Packer

First add your public key replacing the content in the file uploads/root_authorized_keys
(A good tutorial on generating ssh key pairs: https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2)

Then you are all set to go. Using the terminal go into the cloned repo directory and run 

```
packer build ubuntu.json
```

And you should get the output image in the output-ubuntu1604 directory!

## Configuration

The main configuration file is the ubuntu.json file. It contains the versions, ssh hostnames, passwords ..etc for the DC. 
For further changes, you will have to refer to the individual scripts (in the scripts directory). 

#### Validating Configurations

After changes to the ubuntu.json file, you can validate the configuration by running, 

```
packer validate ubuntu.json
```


#### Default Packages installed

Oracle JDK 8
R 
Spark (/opt/spark) 
Anaconda (/opt/anaconda) 
VoyantServer (/opt/VoyantServer) 
Scala 
SBT 
Pytables

#### System level packages: 
git maven python-pip parallel curl htop iotop jq pcregrep zsh python3-pip

#### Libraries installed for both python 2.7 and 3: 
numpy scipy matplotlib pandas nltk regex GenSim ujson dask toolz theano csvkit htrc-feature-reader

## Contributing

Please send Pull Requests for this repo for any changes required. 