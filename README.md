# Jupyter-Lab-on-Mac-Os-with-Proton-Drive-Now-With-Obsidian
This is a guide on how to install jupyer lab with homebrew on macos and set a default directory to a synced proton drive folder.


## Where to Get and What we Have
- [Jupyter Downloads]( https://jupyter.org/install)
- Since I have homebrew on the mac, ill use the homebrew install [here](https://formulae.brew.sh/formula/jupyterlab#default)
- We have Mac Os Ventura and homebrew installed


## Installing

Run 
```
brew install jupyterlab

```

Install ran fine

## Running

To start the jupyer lab server I ran 

```
jupyter-lab
```

The site is openable at 

https://localhost:8888

The [[Proton Drive]] folder is located at /Users/crest/Library/CloudStorage/ProtonDrive-Crest@koemel.net-folder/Coding

## Opening to the folder we want
We want to open to the coding folder by default so let us set up a config file in jupyter to open to our coding directory in proton drive

We'll refer to [this](https://www.roelpeters.be/how-to-change-the-jupyter-notebook-default-directory/) (note that the notebook dir is deprecated but the bones are good)

we run 

```
jupyer-lab --generate-config

nano /Users/crest/.jupyter/jupyter_lab_config.py
```


then edit the config to

```
c.ServerApp.root_dir = ''

to

c.ServerApp.root_dir = '/Users/crest/Library/CloudStorage/ProtonDrive-Crest@koemel.net-folder/Coding'
```

Now when we run 

```
jupyter-lab
```

it opens up to our desired directory
