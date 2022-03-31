CryoEM Sweden Facility Documentation
====================================
This repository contains documentation pages with information for the Facility users
Check it online at: https://cryoem-sweden.github.io/docs/

Building the documentation (requires GitHub user)
-------------------------------------------------

* Install anaconda (or any other Python)
* Create a new environment (e.g conda create --name cryoem-docs)
* Install deps: `pip install sphinx sphinx-readthedocs sphinx_rtd_theme`
* Clone repository: `git clone git@github.com:cryoem-sweden/docs.git`
* cd docs
* make html

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
  




