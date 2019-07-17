---
title: How to run both R and Python in Jupyter Lab session with Anaconda
author: Stephan Jacobs
date: '2019-07-17'
slug: how-to-run-both-r-and-python-in-jupyter-lab-session-with-anaconda
categories:
  - IDE
  - R
tags:
  - R
  - Python
  - Jupyter Lab
  - conda
---

So full disclosure, most (*most*, not all) of what I'm telling you below is based on [this very helpful page from the Anaconda docs](https://docs.anaconda.com/anaconda/navigator/tutorials/r-lang/)

But the point of writing this guide is to give you some other useful information along the way :)

## Getting started

The first thing you need to do is create a new conda environment. This basically
 means you have a special folder somewhere that contains a **totally different**
 set of installed packages. Everything from numpy to dplyr goes in there.

>Yes the R things and Python things are in the same folder, but there's a catch. See below ;)

So if you have some Python stuff in your conda environment already, and some
R packages you've already installed before creating this new conda environment
then it doesn't make an ounce of a difference. Consider this new environment to
be basically starting from scratch.

Anyhoo, follow the instructions in [that link up there](https://docs.anaconda.com/anaconda/navigator/tutorials/r-lang/) to get started.

Done? Good!

>**The catch**
>
>*All the R packages simply have 'r-' prepended to their name*
>
>So for Python do: `conda install matplotlib`
>And instead for R: `conda install r-ggplot2`

## Install all the packages you want to use for Python

You know, pandas, numpy, matplotlib, whatever it is you always use. And if
there's a weird package you need for just the one project, environments are a
*great* way of organising that.

>So I just install my new packages the way I always do?

**NO!**

You install them the special way!

The full details of the special way can be found [here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) but I'll give you the most
important things:

#### 1. Create new conda environent

As per the [instructons at the top](https://docs.anaconda.com/anaconda/navigator/tutorials/r-lang/).

For this example we'll call it `ProjectAwesomeEnvironment`, but in real life
you'll probably want to stick to something a bit shorter.

#### 2. Activate that environment:

```bash
C:\> conda activate ProjectAwesomeEnvironment
```

At this point, if you're using Anaconda prompt in Windows you might see something like:
```bash
(ProjectAwesomeEnvironment) C:\>
```

#### 3. Intall your packages:
```bash
(ProjectAwesomeEnvironment) C:\> conda install pandas
```
```bash
(ProjectAwesomeEnvironment) C:\> conda install r-dplyr
```

#### 4. Finish up

Once you're done you can either:

1. simply close the command prompt
2. exit/deactivate the environment like so:
```bash
(ProjectAwesomeEnvironment) C:\> conda deactivate
```

**You're set!**


## Now to do your actual work:

#### 1. Select your environment in Anaconda navigator

You might notice that the applications on Anaconda's homepage are different
depending on which environment you're on. That's ok! Just click *Install* for
whichever application you want in that environment.

For a combined R and Python environment you will very likely be interested in
both Jupyter {Lab, Notebooks}, and RStudio. But hey, don't let me tell you how
to live your life.

#### 2. Launch the application you want to work with
This makes sure that whatever your preferred Anaconda distributed application
might be, it's looking at the right set of packages. The one that you've
painstakingly put together

## 🐒
