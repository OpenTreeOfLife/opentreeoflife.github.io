---
layout: page
title: Updating the supertree
permalink: /updatetree/
---


## Prep

  1. Build <a href="https://github.com/OpenTreeOfLife/otcetera">otcetera</a>. You can look at 
 https://files.opentreeoflife.org/synthesis/opentree16.1/output/index.html#configuration-tools to look for the otcetera SHA used for the synth build of tree 16.1

  2. Install <a href="https://github.com/OpenTreeOfLife/peyutil">peyutil</a> (last used SHA ffcc8836b402f527fb6397f6420dad8c18b432a9)

  3. Install <a href="https://github.com/OpenTreeOfLife/nexson">nexson</a> (last used SHA 18bb5f52aa9bc745a8bab83af3a996ea3f794c62)

  4. Install <a href="https://github.com/OpenTreeOfLife/git_wrap_opentree">git_wrap_opentree</a> (last used SHA 89b1f23449459ed49024f111507b380e30e9dc33)

  5. Install <a href="https://github.com/OpenTreeOfLife/peyotl">peyotl</a> (last used SHA da27fa12f7a2664f266e2798b62fd8214f961571)

  6. Install <a href="https://github.com/OpenTreeOfLife/propinquity">propinquity</a> For last SHA used see https://tree.opentreeoflife.org/about/synthesis-release/v16.1 

  

# Workflow

## Update the propinquity config file

Edit (then save and commit), "${OPENTREE_ROOT}/propinquity/config/full.json" to refer to the version of OTT that you want to use and adjust collections and flags (if needed)

## Fetch studies from collections-1

    cd "${PHYLESYSTEM_PAR}/collections-1"

## Fetch studies from phylesystem-1

    cd "${PHYLESYSTEM_PAR}/phylesystem-1"


## Build the tree

The arguments to `checkpoint_then_check.bash` specify (1) the location of config, (2) the output parent directory, (3) the name+version number of the tree, and (4) the number of cores to use in the snakemake process

    cd "${OPENTREE_ROOT}/propinquity"
    bash checkpoint_then_check.bash \
        "${PWD}/config/full.json" \
        "${OPENTREE_ROOT}/results" \
        opentree16.1 \
        20

## Create summaries of comparison to previous run

This assumes that you have the previous version downloaded locally. For instance to compare version 16 to 15 (and store the results in a "${OPENTREE_ROOT}/cruft" directory), MTH used:

    cd "${OPENTREE_ROOT}/propinquity"
    bin/compare_synthesis_outputs.py \
      --html-dir="${OPENTREE_ROOT}/cruft/d15to16" \
      -b \
      -t \
      -v \
      "${OPENTREE_ROOT}/results/opentree15.2" \
      "${OPENTREE_ROOT}/results/opentree16.1"

This will create the following files in the output directory:

  * `broken_taxa_report.csv`
  * `index.html`
  * `summary.html`
  * `trees_by_new_broken.html`

`trees_by_new_broken.html` is quite helpful in identifying newly included trees that are breaking major clades.