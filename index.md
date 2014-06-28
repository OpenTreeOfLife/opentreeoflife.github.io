---
title: Open Tree of Life on GitHub
---

#Open Tree of Life

Main project site: [http://opentreeoflife.org](http://opentreeoflife.org)

GitHub: [http://github.com/opentreeoflife](http://github.com/opentreeoflife)

##Main stack of Open Tree of Life

These are the repositories that form the core infrastructure:

* **opentree**: web application for tree browsing and curation
* **phylesystem, phylesystem-api, oti**: input tree document store, index and APIs
* **treemachine, taxomachine**: graph databases for trees and taxonomy; implement synthesis methods and APIs

##Deployed repositories

* **opentreeoflife.github.io** : This web page.

* **opentree** : Open Tree of Life web application at  tree.opentreeoflife.org (dev version at devtree.opentreeoflife.org). Includes tree browsing and curator functionality. Written using web2py.  

* **phylesystem** : The top-level repository in the Open Tree of Life phylogenetic study document store. The data are actually stored in different repositories - phylesystem-1, phylesystem-2, etc - which we refer to as shards. This is to future proof against repository size limits in GitHub. 

* **phylesystem-1** : 
Contains the NexSON files for the phylogenetic study document store, organized into subdirectories. Each NexSON file represents one study (publication), and may contain more than one tree. Currently the only phylesystem shard repository. 

* **oti** : A neo4j graph database that provides indexing services for the phylesystem NexSON data store. 

* **peyotl** : A python library that implements many of the Open Tree of Life APIs. 

* **phylesystem-api** : The API layer for interacting with the NexSON data store. A web2py application. 

* **reference-taxonomy** : Code for merging input taxonomies to create the Open Tree of Life reference taxonomy, OTT. We refer to the merging program as smasher. Combination of python scripts and jython. 

* **treemachine** : Implements synthesis of trees and taxonomy using a neo4j graph database. Written in Java.

* **taxomachine** : The graph database for storage and services for the Open Tree Reference taxonomy. Written in Java.

* **gcmdr** : Scripts for loading data into treemachine. Python.

* **ot-base** : General Java classes for Open Tree of Life development with Neo4j

* **deployed-systems** : Current (and past) server configuration files for opentree components. Includes information on deployemnt of both development, production and a small test system (based on the clade Asterales).  

* **phylografter** : Phylografter was the Open Tree of Life curation app until being replaced by the 'curator' app within the main web application (code in the opentree repo). Still maintained by Rick Ree, implements methods for tree curation and conflict detection. A web2py application.  

* **hackathon** : A repository for the Open Tree of Life hackathon in Ann Arbor in September 2014. Prior to the hackathon, only using issue tracker for discussion of potential hackathon projects. 

* **feedback** : Used only for the issue tracker; feedback from the opentree web application goes here. 


##Repositories in development / for testing only 
* **phylesystem-0** : Document store for testing. Full size - contains all studies. 

* **phylesystem_test** : Document store for testing. Small size - contains only subset of studies. 

* **hbf_phylesystem_test** : Temporary repo of NexSON 1.2.1 to be used for testing the API. 

* **otb** : Deployment scripts that we aren't using yet.

* **opentree-testrunner** : Scripts for testing some of the software tools produced by the Open Tree of Life effort. Planning to put more attention here after v 1.0 release. 

* **taxonomy-stree-json** : Code for visualizaing source trees aligned to taxonomies in [Phylografter](https://github.com/OpenTreeOfLife/phylografter)

##Repositories no longer being used / maintained
* **nexson-sandbox** : 
A set of test NexSON files that we used early in the project. 

* **argus** : 
Argus is a javascript library for displaying large hierarchies. It was designed to work with the Open Tree of Life's treemachine and taxomachine.  The code is still being used and maintained by the Open Tree of Life. In order to simplify the installation and deployment of the software, the code that 
was in this repository has moved to a the [opentree](https://github.com/OpenTreeOfLife/opentree) repo.

* **2nexml** : 
Code for converting NEXUS files to NeXML using the Nexus Class Library. 

* **big-tree-collection-simulator** : 
Code for simulating a collection of input trees based on a classification. Used early in the project, and may be resurrected for future testing. 

* **PhylografterNeo4j** : 
A version of Phylografter using neo4j as the back end. No longer being developed. 

