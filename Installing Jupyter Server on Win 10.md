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


