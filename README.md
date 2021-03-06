# Fundamentals of Radio Interferometry

An ipython notebook-based book on the fundamentals of radio interferometry

If you want to contribute, fork the repository, make changes, and when you are ready, submit a pull request.

## Setup contributor virtualenv

If you would like to contribute to notebooks it is useful to setup a python virtual environment to ensure your environment is consistent with other contributors. This section provides a guide for how to do this in an Ubuntu system (tested on 14.04), other systems should work with slight modifications.

Currently we are using pip to install packages, the most important package versions are:

* pip 7.1.2
* python 2.7.6
* numpy 1.10.1
* matplotlib 1.5.0
* scipy 0.16.1
* ipython 4.0.0
* astropy 1.1.1
* aplpy 1.0

This guide was developed from these references:

* <http://jeffskinnerbox.me/posts/2013/Oct/06/ipython-notebook-in-virtualenv/>
* <http://iamzed.com/2009/05/07/a-primer-on-virtualenv/>
* <http://jonathanchu.is/posts/virtualenv-and-pip-basics/>
* <https://warpedtimes.wordpress.com/2012/09/23/a-tutorial-on-virtualenv-to-isolate-python-installations/>

Before setting up a virtual environment there are a few system level libraries which need to be installed

```
sudo apt-get install libpng-dev libncurses5-dev
```

To setup a clean environment to run our ipython-notebook standard system, start by making sure virtualenv is installed on your system. Run:

```
$ which pip
```

If there is no output, then you need to install pip:

```
$ sudo easy_install pip
```

Next, run:

```
$ which virtualenv
```

If there is no output, then you need to install virtualenv:

```
$ sudo apt-get install python-virtualenv
$ sudo pip install virtualenvwrapper
```

Once you have all the basic packages installed you can create a vitrualenv, I tend to keep all my virtualenvs in one place, e.g. a .virtualenv directory in my home directory

```
$ cd .virtualenv
$ virtualenv --no-site-packages fundamentals
```

This creates a virtualenv called fundamentals in the .virtualenv directory which is completely independent of any system site-packages, to active the virtualenv run the activation script

```
$ cd fundamentals
$ source bin/activate
```

First, lets clone the repository from github, you should use your own forked version if you want to make changes

```
$ git clone https://github.com/[username]/fundamentals_of_interferometry.git
```

If you just want to run the notebooks interactively you can just use this repository.

```
$ git clone https://github.com/griffinfoster/fundamentals_of_interferometry.git
```

Now this is a completely clean environment, there are no python packages installed, we need to set those up. There are two ways to do this, first is by running the following pip install commands, the other is by installing from the requirements file included in the this repository. I recommend the requirements file as it contains current version information. The file is in the main directory of the repository or can be downloaded [here](https://raw.githubusercontent.com/griffinfoster/fundamentals_of_interferometry/master/requirements.txt). This will take a bit of time to setup, I recommend a tea break.

```
$ pip install --upgrade pip
$ pip install -r [path to file]/requirements.txt
```

or

```
$ pip install --upgrade pip
$ pip install yolk
$ pip install numpy
$ pip install matplotlib
$ pip install scipy
$ pip install ipython[all]
$ pip install --no-deps astropy
$ pip install aplpy
```

We are now ready to start the ipython notebook server:

```
$ cd fundamentals_of_interferometry
$ ipython notebook
```

To kill the server, type ctrl-c at the terminal and input y. To deactivate the virtualenv and return to your normal environment run:

```
$ deactivate
```

In the future, when you wish to return to the virtualenv, change to the fundamentals directory and run:

```
$ source bin/activate
```

### Ubuntu 12.04 Issues

The system setuptools/distribute (0.6.24) is not new enough and needs to be updated with easy_install

```
easy_install -U distribute
```
