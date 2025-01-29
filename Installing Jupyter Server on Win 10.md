## Prequistes from [Jupyter](https://jupyter.org/install)
- pip
- want venv
- python 3.10 or higher

## What I'm thinking
Im wondering if I could go a little bad boy on this project and just install jupyter in wsl, probably ubuntu, and then just tcp connection to the server. Lets try. I already have
- ubuntu 24 lts wsl
- virtualization enabled

You can get the ubuntu image from the microsoft store, and I'm using wsl2 for the vm. Terminal is way easier than a gui for me since I like tinkering with vms and I mostly use bash anyways.

## Getting on wsl2 ubunutu 24
Headed to the microsoft store, downloaded and ran.

Ran 

```
apt update 
apt uprade
```

to update the repos.

Lets open up a python3.12 terminal to try out using pip


Pip is not a native install so lets install it with

```
sudo apt install python3-pip
```


Running pip freeze we can see our packages.

Lets install venv in our debian python package so we can manage our enviroments with

```
sudo apt install python3.12-venv
```

Then running

``` 
python3 -m venv wsl-example

```
creates a venv folder in our home dir.

we can activate this virtual environment with 

```
source wsl-example/bin/activate
```

This puts us in a virtual environment.
Running pip freeze we can see no packages installed. 

So lets install jupyter lab with
```
pip install jupyterlab
```

And running the jupyter lab command in the virtual environment we can get the url to the server.
http://localhost:8888/lab?token=faa8ca536a72b6f8ecc5ec776b4860d870f7b3d8e9eaba55

Easy as that. For the need of different packages we can install each set of packages in the venv.