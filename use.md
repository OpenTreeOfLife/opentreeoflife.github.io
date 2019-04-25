---
layout: page
title: Using Open Tree of Life web-services
permalink: /use
---

# R interface to Open Tree

See [https://github.com/ropensci/rotl](https://github.com/ropensci/rotl)
for information about R wrappers for interacting with Open Tree's web services.


# Integrating Open Tree and GBIF
Emily Jane McTavish wrote a tutorial
    [here](https://mctavishlab.github.io/BIO144/labs/rotl-rgbif.html)
covering some ways to use trees from Open Tree with
    geographic range data from GBIF.

# Looking for conflicting phylogenetic claims
Our tree curation tool has a [conflict viewer](https://tree.opentreeoflife.org/curator/study/view/ot_1843/?tab=trees&tree=Tr112663&conflict=ott) that allows you to compare
a tree to the Open Tree Taxonomy or the Open Tree Synthetic tree.
We are in the process of generalizing this feature so that biologists can
    compare any tree to any other tree.
These trees will need to be mapped to the Open Tree Taxonomy.

# API Docs
Our current API is documented at [here](https://github.com/OpenTreeOfLife/germinator/wiki/Open-Tree-of-Life-Web-APIs)