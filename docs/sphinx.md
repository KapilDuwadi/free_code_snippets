### Using sphinx for python documentation

#### Install Sphinx

```
pip install sphinx
```

#### Install themes and extensions

I like press theme and typically use Googles style code. If you are using Googles style for documenting 
you need to install nepoleon extensions. 

```
    pip install sphinxcontrib-napoleon
    pip install sphinx-press-theme
```

#### Create a sphinx skeleton

Create a `docs` directory in the root folder. Cd into the directory and run the following command

```
sphinx-quickstart
```

#### Edit the conf.py file

First uncomment and edit the imports

```
import os
import sys
sys.path.insert(0, os.path.abspath(".."))
```

```
extensions = ["sphinx.ext.autodoc", "sphinxcontrib.napoleon"]
html_theme = "press"
```

#### Now let's run sphinx apidoc

Use the following command to generate python documentation automatically. Assuming you are
in `docs` folder.

```
sphinx-apidoc -f -o . ../src
```

#### Edit index.rst file

Add the modules.rst in the index.rst file.

```
.. toctree::
   :maxdepth: 2
   :caption: Contents:

   modules.rst
```

#### Create the HTML

Run the following command to create HTNL file

```
sphinx-build -b html . sphinx_doc
```