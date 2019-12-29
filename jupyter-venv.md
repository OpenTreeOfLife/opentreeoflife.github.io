---
layout: page
title: To run Jupyter notebooks in a virtal environment
permalink: /jupyter-venv
---



<pre>
cd python-opentree  
virtualenv -p python3 venv-jupyentree  
source venv-jupyentree/bin/activate  
pip install -r requirements.txt  
python setup.py develop  
pip install ipykernel  
python -m ipykernel install --user --name=opentree  
pip install jupyter  
jupyter notebook  
</pre>


Then select "opentree" from the new notebook dropdown