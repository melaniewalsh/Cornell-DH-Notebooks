# Cornell DH Notebooks

This is the start of our Jupyter Book project for the Cornell DH Notebooks Series.

The Python package [`jupyter-book`](https://jupyterbook.org/start/build.html) will process the Jupyter notebook files (.ipynb) from this repository and output them as publication-quality HTML files for our [corresponding website](https://melaniewalsh.github.io/Cornell-DH-Notebooks/).

The HTML files are currently hidden in this branch of the GitHub repository, but you can find them in the [gh-pages branch](https://github.com/melaniewalsh/Cornell-DH-Notebooks/tree/gh-pages), which generates our website.

## How to add to this book

If you'd like to add a notebook to the Cornell-DH-Notebooks Jupyter Book, you should:

- Clone this repository 
- Run `pip install -r requirements.txt` 
- Add your notebook to the correct issue directory, e.g., `jupyterbook/notebooks/Issue-1`
- Run `jupyter-book build jupyterbook/`

A fully-rendered HTML version of the book will be built in `jupyterbook/_build/html/`. You can push these HTML files to our website by pushing them to the `gh-pages` of this repository. To do so, you can [install `gh-import`](https://jupyterbook.org/publish/gh-pages.html#push-your-book-to-a-branch-hosted-by-github-pages) and then run `ghp-import -n -p -f jupyterbook/_build/html`

## What's in this repository?

Below I will briefly explain the structure of this repository and some important Jupyter Book features. All the materials that generate our Jupyter Book can be found in the directory `/jupyterbook`.

### Configuration file

The configuration file `/jupyterbook/_config.yml` is where we establish key features of the book, such as its title and logo as well as whether we want to be able to open our Jupyter notebook files in the cloud.
 
### Table of Contents file

The table of contents file `/jupyterbook/_toc.yml` establishes the table of contents structure on the left-hand side of the web page. To include a markdown or Jupyter notebook file in the table of contents, you include the flag `- file:` followed by the path to the file *without* the file extension, as shown below: 
```
- file: notebooks/intro

- part: How To
  chapters:
  - file: notebooks/How-To-Interact-With-This-Series
    title: Interact With This Series
    
- part: Issues
  chapters:
  - file: notebooks/Issue-1/intro
    title: Issue 1
    sections:
      - file: notebooks/Issue-1/Mapping-Kate-Chopin 
```

If you want the title in the table of contents to be different from the file path, you can also specify a `title` below the `- file:` flag. You can also include headers within the table of contents by using the `- part` flag or collapsed chapters by including `chapters:`.

### Notebooks

The Jupyter notebook files can be found in `jupyterbook/notebooks`

### Data

Data can be can be found in `jupyterbook/data`

## Credits

This project is created using the excellent open source [Jupyter Book project](https://jupyterbook.org/) and the [executablebooks/cookiecutter-jupyter-book template](https://github.com/executablebooks/cookiecutter-jupyter-book).
