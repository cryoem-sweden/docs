CryoEM Sweden Facility Documentation
====================================
This repository contains documentation pages with information for the Facility users
Check it online at: https://cryoem-sweden.github.io/docs/

Building the documentation (requires GitHub user)
-------------------------------------------------

**Step 1:** Install anaconda ( or miniconda)

**Step 2:** Create a new environment and install dependencies

.. code-block:: bash

    conda create -y --name=cryoem-docs python=3.8
    conda activate cryoem-docs
    pip install sphinx sphinx_rtd_theme
    
**Step 3:** Clone the repository and build docs

.. code-block:: bash

    git clone git@github.com:cryoem-sweden/docs.git
    cd docs
    make html


Updating the documentation (requires GitHub user)
-------------------------------------------------

Before updating the documentation, make sure you are able to build the docs as 
stated in the previous section. Then follow these steps:

**Step 1:** Update your local folder with latest changes

.. code-block:: bash

    cd /path/to/docs
    git pull --prune
    
**Step 2:** Make changes: edit existing files or add new ones (including images). Then build the documentation:

.. code-block:: bash

    make html # (or make clean html for a complete rebuild)
    
**Step 3:** Review generated html at: /path/to/docs/_build/html/index.html. Then commit the changes.

.. code-block:: bash   
   
    git add .
    git commit -m "Messages about your changes"
    git push 
  
  
Publishing the changes online (requires GitHub user)
----------------------------------------------------

**Step 1:** Update 'master' branch with latest changes.

.. code-block:: bash

    cd /path/to/docs
    git checkout master
    git pull --prune

**Step 2:** Merge 'master' branch into 'html' one and build the docs.

.. code-block:: bash

    git checkout html
    git merge master
    make html # (or make clean html for a complete rebuild)
    Review generated html at: /path/to/docs/_build/html/index.html
    
**Step 3:** Copy build into 'docs' folder of the 'html' branch and push changes.

.. code-block:: bash

    # Copy generated files from _build/html to internal docs folder
    rsync -av _build/html/ docs/
    git commit -am "New release of the documentation"
    git push
   
