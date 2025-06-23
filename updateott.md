---
layout: page
title: Update OTT
permalink: /updateott/
---


## Prep

  1. Build <a href="https://github.com/OpenTreeOfLife/otcetera">otcetera</a>. The main/master branch should
   be fine. If that doesn't work, check the details from the last successful patch. Hopefully they are in
   a JSON file the <a href="https://github.com/mtholder/OTifacts/tree/master/ott">OTifacts OTT</a> directory. There should be a `source` blob with `"github_repository": "OpenTreeOfLife/otcetera"` and a `SHA` property that documents the last otcetera SHA.

  2. Pull the latest changes from <a href="https://github.com/OpenTreeOfLife/amendments-1/">amendments-1</a>

  3. Pull the latest changes from <a href="https://github.com/OpenTreeOfLife/edOTTs/">edOTTs</a>

  4. Get a Python virtual env into which you has installed the latest versions of <a href="https://github.com/OpenTreeOfLife/peyutil/">peyutil</a>, <a href="https://github.com/OpenTreeOfLife/nexson/">nexson</a>, and <a href="https://github.com/OpenTreeOfLife/git_wrap_opentree/">git_wrap_opentree</a>.

# Workflow

## Create an `edOTT` 
The `otc-taxonomy-patcher` does not read all of the details of the taxon amendments file. You have to bundle the taxon amendments into one blob that simplifies them and conducts some checks that would be tedious to do in C++

  1. Figure out the SHA of the commit of the **amendments-1** repo was that at when the most recent edOTT##.json file was created. Ideally this would be in <a href="https://github.com/OpenTreeOfLife/edOTTs/blob/main/README.md">the edOTTs README.md</a>; the OTifacts file mentioned above may have it, if it is not present.

  2. Let's call this SHA LAST_INCORPORATED_SHA

then you can run (assuming that you have all of the `amendments-1`, `otcetera`, and `edOTTs` repos as children of `${OPENTREE_ROOT}`

    cd ${OPENTREE_ROOT}
    ${OPENTREE_ROOT}/otcetera/scripts/semanticize_amendments.py amendments-1 LAST_INCORPORATED_SHA > ${OPENTREE_ROOT}/edOTTs/edott-#####.json 

where you substitute the actual SHA for `LAST_INCORPORATED_SHA`. Make sure that command succeeds.

Note that `semanticize_amendments.py` is a terrible name. It was going to be a semantic analysis, but started with just some syntax operations; and that is as far as it has gotten.

## Patch OTT
At this point, I run a bash script from the edOTT directory. It does not really matter
what directory you are in when you run this, but your directory **must be the parent** of a directory named `cruft` to hold the ouput messages.

The bash script is equivalent to the following commands.
First, you set some env variables that will depend on your setup and the OTT versions you are dealing with:


    export OPENTREE_ROOT="${HOME}/opentree"
    export PREV_OTT_DIR="${OPENTREE_ROOT}/ott/ott3.7.2"
    export NEW_OTT_DIR="${OPENTREE_ROOT}/ott/ott3.7.3"
    export NEW_OTT_VERSION="3.7draft3"
    export NEW_EDOTT_FILENAME="edott-000015.json"

Note in these examples, I have an `ott` directory below `OPENTREE_ROOT` which holds the full (uncompressed) versions of the OTT taxonomies.

With those variables set you should be able run:


    rm -f "${NEW_OTT_DIR}/forwards.tsv"
    rm -f "${NEW_OTT_DIR}/synonyms.tsv"
    rm -f "${NEW_OTT_DIR}/taxonomy.tsv"
    rm -f "${NEW_OTT_DIR}/version.txt"

    otc-taxonomy-patcher   \
      --demand-all-applied \
      --edits "${OPENTREE_ROOT}/edOTTs/${NEW_EDOTT_FILENAME}" \
      "${PREV_OTT_DIR}" \
      --write-taxonomy "${NEW_OTT_DIR}" 2>&1 | tee "cruft/patch-${NEW_OTT_VERSION}.log" || exit
    echo "${NEW_OTT_VERSION}" > "${NEW_OTT_DIR}/version.txt"
    rm otc-taxonomy-patcher.log.txt

The first `rm` commands are just a good idea in case you have to patch multiple times.

## Check that the run was successful

If the run was successful, there should be some line like:

    X/X amendments applied.

in the output where X is the number of amendments in the edOTT file and **all** of them were successfully applied.

Sometimes, a taxon gets added multiple times. The curator/api should prevent this, but it does not always work. When this happens, you'll see a line like:

    amendement #12 not applied: Protanilla boltoni is a homonym of 6520522

which indicates that `Protanilla boltoni` was added by an earlier amendment with the OTT ID 6520522, but a new amendment tries to give it a new name.  When this happens, I:

  1. Remove the latter amendment
  2. Check the `amendments-1` repo to find the study affected (so that I can remap the mis-mapped taxon later). I store that info in `post-patching-edits-TODO.txt`
  3. Repeat until `otc-taxonomy-patcher` runs successfully

## Commit and push edOTT
  1. Note the current HEAD of the amendments-1 repo in the commit and README.md


## scp OTT to to files.opentreeoflife.org
e.g.

    tar cfvz ott3.7.3.tgz ott3.7.3
    scp ott3.7.3.tgz files.opentreeoflife.org
    ssh files.opentreeoflife.org

then move the archive to the appropriate apache-served directory on that server.

## back up OTT to AWS S3 storage

## Rebuild the synth tree
See <a href="./updatetree/" target="_blank">Update Tree</a>.

## Create a new ott#.#.md doc in reference-taxonomy/doc
Markdown documentation of the OTT build. The output of the synth is useful for getting the number of visible taxa in OTT.

## Create a new ot-synthesis-v#.#.md doc in germinator/doc
Markdown documentation of the tree build.


## Deploy the synth tree and OTT

## Fix any mapping errors
If you have any notes in `post-patching-edits-TODO.txt`, use the curation app to fix them.

