---
title: SSB2023 - Custom Synthesis
layout: workshop      # DON'T CHANGE THIS.
venue: " Synthesizing and dating phylogenies using the Open Tree of Life, SSB UNAM 2023"        # brief name of host site without address (e.g., "Euphoric State University")
address: ""      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
humandate: "Jan 13, 2023"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "10 am - 2 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
instructor: ["Mark Holder", "Emily Jane McTavish", "Luna Luisa Sanchez Reyes", "Ben Redelings"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
email: ["ejmctavish@ucmerced.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
permalink: /CustomSynthesis/
---

*We have borrowed the Carpentries website template and installation instructions. This is **not** a Carpentries workshop (although we highly recommend them!). Learn more about the carpentries at https://carpentries.org/*

See https://opentreeoflife.github.io/SSBworkshop2023/ for the schedule to the full workshop.

<h2 id="general">The Open Tree of Life "synthetic tree"</h2>


The Open Tree of Life project
produces a supertree estimate of the full tree of Life.
This tree has been called the Open Tree "synthetic tree", 
but "supertree" would be a more specific name.

A supertree is a phylogenetic estimate that uses input trees
as the data source for the estimation.
Typically the input trees are not taxonomically complete - they 
each only contain a subset of the full collection of species. 
However the output tree contains all of the species mentioned in any of the input trees.

See <a target="_blank"  href="https://peerj.com/articles/3058/">https://peerj.com/articles/3058/</a> (and subsequent papers by Redelings and Holder) for the details of how the 
supertree is constructed. 
The most important features to be aware of are:
<ol>
  <li>The algorithm builds a synthetic tree by adding as many groupings from the input trees as it can.</li>
  <li>The order of the input trees matters. Addition of grouping occurs according to the order of trees in the input list.</li>
  <li>The Open Tree Taxonomy is used as the last input tree - so the output will be as comprehensive as the Open Tree Taxonomy.</li>
</ol>


<h2 id="general">"Custom synthesis"</h2>
In this workshop, we will use a new (and relatively untested)
interface that allows you to apply the Open Tree of Life synthesis pipeline to a set of trees of your choosing.

The fundamental steps are:
<ol>
  <li>Store an (ordered) list of input trees in a "collection"</li>
  <li>Choose the root taxon for the analysis (<strong>Please</strong> do not conduct analyses of over 10,000 species during the workshop, because we will all be sharing computational resources).</li>
  <li>Submit those inputs to the server</li>
  <li>Download the results</li>
</ol>

<hr />

<h2 id="collection">#1 Creating an input collection</h2>

The input trees have to be in curated in the Open Tree of Life's corpus of published trees. Fortunately, you just had a tutorial on how to add trees to that database.

<h3>1A. Find input trees</h3>

If you know what trees you want to include, just make sure that you know the "Study ID" and "Tree Name" for each tree.
Or you can conduct a search for trees that include a taxon.

To search you can use the search box on <a href="https://tree.opentreeoflife.org/curator/" target="_blank">https://tree.opentreeoflife.org/curator/</a>, though that will only return studies tagged with the taxon name in some crucial fields.

To do a more thorough search, you can:

<ol>
  <li>Navigate to <a target="_blank"  href="https://tree.opentreeoflife.org/taxonomy/browse">https://tree.opentreeoflife.org/taxonomy/browse</a> and use
    the search box to find the taxon you want. <strong>Write down it's OTT ID</strong> (this ID is in the "Taxon details" section of the page).</li>
  <li>Use the Open Tree web-service API to search for trees that include that taxon.
    For instance I found that <a target="_blank" href="https://tree.opentreeoflife.org/taxonomy/browse?name=Primates">the taxon Primates has the the OTT ID of 913935)</a>.
    So (from a terminal) I can run the command:
<pre>
curl -XPOST https://api.opentreeoflife.org/v3/studies/find_trees -H "content-type:application/json" \
  -d '{"property":"ot:ottId", "value":913935, "verbose":true}'
</pre>
   to find trees that include primates.</li>
</ol>

For this exercise: <strong>Make sure you know the (Study ID, Tree Name) pairs for at least 2 trees</strong>.
Note: if you use the API search, the "Tree Name" is the "@label" field of the response. 

<h3>1B. Create a new collection</h3>
Click on your user name at the top-right of <a target="_blank" href="https://tree.opentreeoflife.org/curator">https://tree.opentreeoflife.org/curator</a> to reveal the menu and choose "My collections".

<img src="/images/curator-my-collections.png" alt="screenshot of the top banner of the curator app, showing the drop-down menu from the user-name" width="700px"/>


This will take you to your curator's profile, which has a URL
similar to:
<tt>https://tree.opentreeoflife.org/curator/profile/mtholder#collections</tt>
except with your username in place of <tt>mtholder</tt>.

<strong>Click "Create new tree collection" button</strong> to create the list of trees to use. Choose a simple name (just letters and number) for the collection.

<strong>Save</strong> the collection. This should redirect you
to a full-screen page for adding trees to the collection.

Add trees by repeatedly:
<ol>
  <li>Clicking on the "Add a tree to this collection" button</li>
  <li>Clicking on the magnifying glass button near the "by matching a study" prompt.</li>
  <li>Typing in the study ID (starting with <tt>pg_</tt> or <tt>ot_</tt>) in the box</li>
  <li>Clicking on the study citation when it appears by the box</li>
  <li>Choosing the tree name from the drop down menu</li>
  <li>Clicking on the "+" button</li>
</ol>

<strong>Reorder</strong> you trees using the rank column, if you added them in an order that you don't like.

<strong>Save</strong> the collection ("Save Collection" button near the top).

<h2>#2 Choose your root taxon</h2>
Use <a target="_blank"  href="https://tree.opentreeoflife.org/taxonomy/browse">https://tree.opentreeoflife.org/taxonomy/browse</a> 
to find the Open Tree of Life Taxonomy's name for taxon that is of interest to you.

Presumably all of the trees that you put in the collection would contain some members of this taxon, but the taxon need not include the entirety of the input trees. The synthesis algorithm will trim the input trees down so that only portions relevant to this taxon will be used.

<strong>Please</strong> do not conduct analyses of over 10,000 species during the workshop, because we will all be sharing computational resources

<strong>Note the OTT ID</strong> of the taxon, too.


<h2>#3 launch a custom synthesis run</h2>
We have not fully tested the custom synthesis procedure yet, so it is on a testing server at the moment.

Direct your web browser to <a href="https://ot38.opentreeoflife.org/v3/tree_of_life/launch_custom" target="_blank">https://ot38.opentreeoflife.org/v3/tree_of_life/launch_custom</a>


<ol>
  <li>Select your user name after the "Collection to use:" label</li>
  <li>Select the name of the collection that you want to use. If you don't see your collection: make sure that you saved it, and use the "Refresh list of collections" button</li>
  <li>Start to type the root taxon name in "Search for name" and pause after the first few letters to allow it to autocomplete the name. You may have to add more letters to narrow down the options.</li>
  <li>Select the name of the taxon when you have found it in the autocomplete list. This should fill in the OTT ID field.</li>
  <li>If everything looks correct, click the "Request build for..." button <strong>only once</strong>
</ol>

That should redirect you to a page (with a URL that starts with https://ot38.opentreeoflife.org/v3/tree_of_life/browse_custom) which highlights the synthesis run you just requested.

You can use the "Refresh" button to update the status. Hopefully, it will eventually go to "COMPLETED."

If the status changes to "REDIRECTED" it means that the server detected the same root taxon and the same set of input trees in another run, so it will give you a link to that previous run (rather than recomputing the synthesis).

This is still a testing service. So, if the status changes to "FAILED", please let us know by filling out the fields of a new issue with the 
synth_id that failed <a href="https://github.com/OpenTreeOfLife/feedback/issues/new/choose">in this GitHub issue tracker</a>.