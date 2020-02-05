---
title: Open Tree AmphibiaWeb
layout: workshop      # DON'T CHANGE THIS.
venue: "Using and Building the Open Tree of Life"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Hotel Indigo"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
humandate: "Feb 28, 2020"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "12 pm - 4 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
instructor: ["Emily Jane McTavish","Luna Luisa Sanchez Reyes"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
email: ["ejmctavish@ucmerced.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
permalink: /AWworkshop/
---

*We have borrowed the Carpentries website template and installation instructions. This is **not** a Carpentries workshop (although we highly recommend them!). Learn more about the carpentries at https://carpentries.org/*


<h2 id="general">Registration</h2>

<strong>[Fill in this survey to register for the workshop](https://ucmerced.az1.qualtrics.com/jfe/form/SV_elKXmtHUgYEa097)</strong>
There's free lunch!  



<h2 id="general">Using and Building the Open Tree of Life</h2>


The [Open Tree of Life project](http://opentreeoflife.github.io/) is a phylogenetic resource that offers a synthetic tree summarizing evolutionary relationships across 2.6 million taxa. OpenTree (as of September 2019) also provides access to 4,168 published studies comprising 9,367 trees, and the database is growing weekly. The tips of these trees are mapped to taxonomic identifiers that link across taxonomic and informatics databases such as NCBI and The Global Biodiversity Information Facility (GBIF).
The website also provides user-friendly resources for bulk reconciliation of taxonomic names to these standardized identifiers. Together these resources offer a formidable suite of tools and data for taxonomic name reconciliation and phylogenetic comparisons and analyses.
 This workshop will cover how to understand, access and apply these data resources from the Open Tree of Life project to your research questions. Topics will include accessing phylogenetic relationships for arbitrary sets of taxa, applying date estimates to these trees, linking phylogenetic and geographic information, assessing conflict between phylogenetic estimates, and incorporating your own phylogenetic estimates into the OpenTree of Life project.
    The workshop will include interactive browser based exercises, demonstrations of how to access OpenTree data through the API, and tutorials in R and Python. Experience using a command line interface, R or Python will be helpful, but is not required.             


{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong>

  <ul>
    <li>Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>). Run the <a href="#Installation checks">Installation checks</a> to make sure everything is working in advance of the workshop </li>
    <li>Bring a recently published tree of interest to you if you can access one (newick or nexus format)</li>
    <li>Create a Github account if you don't have one. <a href="https://github.com/join">Github</a>. </li>  
  </ul>
</p>

{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates is required to conform to the <a href="https://systbiol.github.io/ssb2020/code_of_conduct.html">Code of Conduct</a>.
</p>

<h2 id="notes">Collaborative Notes Document</h2>

<p>
We will use this <a href="https://etherpad.wikimedia.org/p/OpenTreeSSB">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code. Please sign in!
</p>
<hr/>


<h2 id="schedule">Draft Schedule (subject to change based on interest)</h2>


<div class="row">
  <div class="col-md-6">
    <table class="table table-striped">
    <tr> <td>12:00</td>  <td>Lunch</td> </tr>
    <tr> <td>12:30</td>  <td>Intro to OpenTree</td> </tr>
    <tr> <td>12:50</td>  <td>Supertree synthesis</td> </tr>
    <tr> <td>1:10</td>  <td><a href = "https://github.com/snacktavish/OpenTree_SSB2020">Bulk TNRS, induced subtrees and study search in Python</a></td> </tr>
    <tr> <td>1:45</td>  <td>Coffee break</td> </tr>
    <tr> <td>2:00</td>  <td><a href = "https://lunasare.github.io/ssb2020_workshop/index.html">Getting synthetic trees and dates in R</a></td> </tr>
    <tr> <td>3:00</td>  <td><a href = "https://tree.opentreeoflife.org/curator">Adding trees to OpenTree</a></td></tr>
    <tr> <td>4:00</td>  <td>END</td> </tr>
    </table>
  </div>
</div>

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in this workshop,
  you will need to be able to access RStudio, Python3 and Jupyter notebooks, and use git to clone repos.
  In addition, you will need an up-to-date web browser.

  If you already have these software installed and accessible on your laptop, please skip to the bottom and run the checks.
  Otherwise there are installation instructions listed below.
</p>

<p>
  The Carpentries maintains a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "https://github.com/carpentries/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>


{% include setup.html %}

<h2 id="Installation checks">Installation checks (Please complete before the workshop starts)</h2>
<p>


<h3 id="git check">Git check</h3>

You should be able to open a terminal window and run:

<pre>
    git
</pre>

This should print out some text that starts with "usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]"
<h3 id="Jupyter check">Jupyter check</h3>

<pre>
    jupyter notebook
</pre>

This should open up a browser window that says "jupyter" at the top. If you click on 'new' in the upper right, there should be an option to create a python3 notebook.

(You can close this window and close the terminal.)  


<h3 id="RStudio check">RStudio check</h3>

<p>  
  Open RStudio. Click in the 'console' window. (It's the one with the '>')  

 Run:  

 <pre>
    > version$version.string
    > install.packages("rotl")
    > install.packages(c("devtools", "ape", "stringr"))
    > devtools::install_github("phylotastic/datelife")

 </pre>

 Make sure your version is at least 3.6.0 or higher.  The r opentree installation output should end with "* DONE (rotl)"

  <br>
If theses checks work, then you are all set!   
 Otherwise, please follow the installation instructions above, and then try these tests again. Contact <a href='mailto:{{page.email}}'>{{page.email}}</a> if you are still having issues.
</p>
