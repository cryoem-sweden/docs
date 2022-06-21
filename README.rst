CryoEM Sweden Facility Documentation
====================================
This repository contains documentation pages with information for the Facility users
Check it online at: https://cryoem-sweden.github.io/docs/

Building the documentation (requires GitHub user)
-------------------------------------------------

**Step 1:** Install anaconda ( or miniconda)

**Step 2:** Create a new environment and activate it

.. code-block:: bash

    conda create --name=cryoem-docs
    conda activate cryoem-docs

**Step 3:** Install required dependencies

.. code-block:: bash

    pip install sphinx sphinx_rtd_theme
    
**Step 4:** Clone the repository and build docs

.. code-block:: bash

    git clone git@github.com:cryoem-sweden/docs.git
    cd docs
    make html

Updating the documentation (requires GitHub user)
-------------------------------------------------

* Make sure you are able to build the docs as stated in the previous section
* cd docs
* git pull  # update with new changes
* edit files or add new files
* make html (or make clean html to completely rebuild)
* Review generated html at: /path/to/docs/_build/html/index.html
* Commit changes: 
  * git add
  * git commit -m "Messages about your changes"
  * git push 
  
Publishing the changes online (requires GitHub user)
----------------------------------------------------

* Update 'master' branch with latest changes
* cd docs
* git checkout master
* git pull  # update with new changes
* git checkout html 
* git make html (or make clean html to completely rebuild)
* Review generated html at: /path/to/docs/_build/html/index.html
* # Copy generated files from _build/html to internal docs folder
* rsync -av _build/html/ docs/
* Commit changes: 
  * git commit -am "New release of the documentation"
  * git push



