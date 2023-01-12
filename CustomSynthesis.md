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

See <a href="https://peerj.com/articles/3058/">https://peerj.com/articles/3058/</a> (and subsequent papers by Redelings and Holder) for the detains  of how the 
supertree is constructed. 
The most important features to be aware of are:
<ol>
  <li>The algorithm builds a synthetic tree by addign as many groupings from the input trees as it can.</li>
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



<h2 id="collection">Creating an input collection</h2>
