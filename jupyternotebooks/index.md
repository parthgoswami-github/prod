# Getting started with Jupyter Notebooks




I started exploring and using Jupyter Notebook earlier this year for a project based on opensource enablement, licensing and operate first. This is the first time ever I was working with a notebook and apparently had to start from sratch right from understanding how it works, how it needs to be installed and finally how it is to be pushed to a repo and publish the work. 

In the process of exploring the tool, I went throught quite a handful of articles and videos. Everyone's way was a bit different than the other and there was no way correct or proper to work around this. Amongst all, I found the below way to be the most effective and clean and hence thought of penning down the learnings create a how-to guide on installing and working with Jupyter Notebooks. 


This article is written based on a MacOS. Haven’t tried on a linux machine. 

###### Jupyter Notebook = JN    //for ease of writing
**Prerequisites:** Install python3 package


## Install and launch JN


First, let’s create a virtual environment to install JN
```
parth@mac Desktop % python3 -m venv jupyter    
parth@mac Desktop % ls
jupyter
```   		   		    


This creates a folder called jupyter in the current dir which has a python virtual env.  

<br/>

To turn the venv on: 
```
parth@mac Desktop % source ~/jupyter/bin/activate
(jupyter) parth@mac Desktop %
```


The jupyter in parenthesis lets us know that we are in our python jupyter virtual environment. 
>**NOTE:** This needs to be turned everytime you need to work with jupyter notebooks. 

<br/>

Now, let’s install the jupyter notebook pkg
`(jupyter) parth@mac Desktop % pip3 install jupyter notebook`

This installs the jupyter and notebook packages.

<br/>

Creating another dir where I will be launching the JN from and where I can create pages. 
```
(jupyter) parth@mac Desktop % mkdir JupyterNotebooks  	 
(jupyter) parth@mac Desktop % cd JupyterNotebooks     	 
(jupyter) parth@mac JupyterNotebooks % pwd
/Users/parth/Desktop/JupyterNotebooks
```
<br/>

Launching JN now

`(jupyter) parth@mac JupyterNotebooks % jupyter notebook .`

This runs a kernel process on the terminal and launches JN from the `JupyterNotebooks` dir in your default web browser. 

{{<admonition note "Note">}}
All and any work you do can be accessed via localhost and is saved locally.  
{{</admonition>}}

<br/>

Click on the new button in the brower’s JN page to create a new page. The page can be a simple text file, a python file with .ipynb extension or markdown page with .md extention. 

Any pages you create are now saved in `JupyterNotebooks` dir. 


<br/>

###### Alright, we have installed and launched JN to create the pages.
###### Now it's time we create a bundled book out of the pages and upload it in a git repo and publish the book. 
<br/>

## Build and Publish the book


Follow the steps mentioned here https://jupyterbook.org/en/stable/start/overview.html 

Install Jupyter Book <br/>
`pip3 install -U jupyter-book`

<br/>

{{<admonition tip "Tip">}}
Jupyter Book comes bundled with a lightweight sample book to help you understand a book’s structure. 
{{</admonition>}}

<br/>

Create a sample book by running the following command:

`$ jupyter-book create mynewbook/`

<br/>

The name mynewbook can be replaced with any other name and create option will create a skeleton of book for you. 

<br/>

Edit/add/modify the pages under this book. 

<br/>

Once you are done with creating pages and have configured _toc.yml and _config.yml, it's time to build the book. 

`$ jupyter-book build mynewbook/`

<br/>

Use the same build option to re-build the book if you make any new changes. 

<br/>

The book is build. Once all the final reviews are done, it can be published in the git repository.

<br/>

Follow the link below to publish the book online. <br/>
https://jupyterbook.org/en/stable/start/publish.html

<br/>

Checkout some of my works based on Jupyter Notebook
<br/>
- [Opensource Enablement](https://parthgoswami-github.github.io/opensource/intro.html)
- [Opensource Licensing](https://parthgoswami-github.github.io/opensource-licensing-testrepo/intro.html)

<br/>

Thank you for reading! 

