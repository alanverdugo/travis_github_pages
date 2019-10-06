# travis_github_pages

### Create an orphan branch named gh-pages.

```
git checkout --orphan gh-pages

git rm -rf .

echo "#Title of Readme" > README.md

git add README.md

git commit -a -m "Initial commit"

git push --set-upstream origin gh-pages
```

### Activate GitHub pages in the repository settings.


### In the development branch, run the Sphinx-quickstart.

```
sphinx-quickstart --author "Alan Verdugo" \
--project "GitHub pages demo" \
--language en \
--release "1.0" \
--ext-autodoc \
--ext-coverage \
--ext-githubpages \
--no-makefile .
```

```
Welcome to the Sphinx 2.2.0 quickstart utility.

Please enter values for the following settings (just press Enter to
accept a default value, if one is given in brackets).

Selected root path: .

You have two options for placing the build directory for Sphinx output.
Either, you use a directory "_build" within the root path, or you separate
"source" and "build" directories within the root path.
> Separate source and build directories (y/n) [n]: n

Creating file ./conf.py.
Creating file ./index.rst.
Creating file ./make.bat.

Finished: An initial directory structure has been created.

You should now populate your master file ./index.rst and create other documentation
source files. Use the Makefile to build the docs, like so:
   make builder
where "builder" is one of the supported builders, e.g. html, latex or linkcheck.
```

### Modify the index.rst file.

Add lines according to the sections that you may want to include.

For example, we can add a "code" section in the index.
```
.. GitHub pages demo documentation master file, created by
   sphinx-quickstart on Thu Sep 12 09:01:50 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to GitHub pages demo's documentation!
=================================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   code

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
```

Since we added a "code" section, we need to add a `code.rst` file.

In this file, add the names of the .py files that have your code.

In this example, we are asking Sphinx to auto generate documentation for `hello_world.py`:
```
Auto Generated Documentation
============================

.. automodule:: hello_world
    :members:
```


### Modify the conf.rst file.

Uncomment the lines that import the os and sys modules.

Uncomment the line just after that, which points to the absolute location of the code.

Example:
```
import os
import sys
sys.path.insert(0, os.path.abspath('.'))
```

Optional, but recommended: Change the default Sphinx theme to something that is more presentable, like the "Read the docs theme":
```
# -- Options for HTML output -------------------------------------------------

# The theme to use for HTML and HTML Help pages.  See the documentation for
# a list of builtin themes.
#
html_theme = 'sphinx_rtd_theme'
```

### Add a .travis.yml file in the repository root directory.


### Add the repository to Travis.




### Add a GitHub token to the Travis environment variables.
