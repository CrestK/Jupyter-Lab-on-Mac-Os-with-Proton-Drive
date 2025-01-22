# Reasons
The reason to run a virtual environment it to aid in the future, incase we need multiple sets of packages, this might simplify managing those separate environments. Presently it just seems like work, but lets see if that work works to prepare for the work.

# Someone better did it better (after the fact)

[Mark Byrne](https://markbyrne.us/author/markbyrne-usaf/), this dude seems awesome, definitely gotta read his blog. 
## Lets try venv
Python3 comes with venv by default, and python3 is default on macos so lets try 

```
python3 -m venv test-env
```

That makes a directory for the env, how can I get that to jupyter?

A knowledgeable person would say to run the activator script using the zsh command . or source.
So I ran source

```
source test-env/bin/activate
```

This activates the virtual environment

it should say something like 
(test-env) crest@macbookair $pwd

now that you are in the virtual environment you download the interactive python module using pip.

```
pip3  install ipykernel
```

Now lets get jupyter to recognize our new kernel, our awesome kernel.

```
python3 -m ipykernel install --user --name=test-2-env
```

Thats right, you install the new kernel.

And it'll inform you in the output terminal with

```
Installed kernelspec test-2-env in /Users/crest/Library/Jupyter/kernels/test-2-env
```

Exactly what we wanna hear, if you can hear terminal output.

Now whenever we want to add packages to our virtual environment we can source the activate file in the venv folder, run pip3 install commands, be happy.

you don't even need to restart the whole jupyter server to refresh the kernel, just refresh the kernel.