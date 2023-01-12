---
title: Open Tree SSB2023
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
permalink: /SSBworkshop2023/
---

*We have borrowed the Carpentries website template and installation instructions. This is **not** a Carpentries workshop (although we highly recommend them!). Learn more about the carpentries at https://carpentries.org/*


<h2 id="general">Synthesizing and dating phylogenies using the Open Tree of Life</h2>


The (Open Tree of Life project)[tree.opentreeoflife.org] provides an integrated set of tools and data resources to make phylogenetic knowledge more accessible across the diversity of life. Participants will learn to use the Open Tree of Life tools and data stores to evaluate and unite phylogenetic inferences to generate taxonomically complete synthetic trees, which they can apply to their individual research questions in evolutionary biology. The focus of this workshop is demonstrating new features of the Open Tree of Life’s infrastructure: services for adding dates to nodes, constructing supertrees from arbitrary sets of trees, and performing generalized conflict analyses. While most of the services and tools demonstrated require only a browser to access, some will require access via a command line. The tools are accessible via Windows, Mac, or Linux devices.

The workshop will cover using Open Tree of Life phylogenetic study curation tools to standardize the taxonomic names and metadata for published phylogenetic estimates. We will demonstrate tools to assess concordance and conflict across different phylogenetic estimates, and between phylogenetic estimates and taxonomic relationships. Using OpenTree’s custom synthesis tools, participants will generate synthetic summary trees for their taxa based on existing phylogenetic inferences. We will apply existing node date estimates to these synthetic trees, and infer date estimates for undated nodes in trees. Together these approaches will provide participants with the skill set to obtain a dated tree for taxa of interest and understand how published estimates disagree with each other with respect to those taxa.     


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
{% endcomment %}

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
Everyone who participates in SSB2023 is required to conform to the <a href="https://www.ib.unam.mx/ib/ssb2023/code-of-conduct/">Code of Conduct</a>.
</p>

<h2 id="notes">Collaborative Notes Document</h2>

<p>
We will use this <a href="https://etherpad.wikimedia.org/p/OpenTreeSSB">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code. Please sign in!
</p>
<hr/>



<h2 id="schedule">Schedule</h2>


<div class="row">
  <div class="col-md-6">
    <table class="table table-striped">
    <tr> <td>9:00</td>  <td>Intro to OpenTree</td> </tr>
    <tr> <td>9:30</td>  <td>Conflict analysis</td> </tr>
    <tr> <td>10:15</td>  <td><a href = "https://tree/opentreeoflife.org/curator">Uploading trees and making collections</a></td> </tr>
    <tr> <td>11:00</td>  <td>Custom SuperTree Synthesis</td> </tr>
    <tr> <td>12:00</td>  <td>Getting dates for nodes and trees</td> </tr>
    <tr> <td>1:00</td>  <td>END</td> </tr>
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
  you will need to be able to access Bash, Python3 and (optionally) Jupyter notebooks, and use git to clone repos.
  In addition, you will need an up-to-date web browser and a text editor.

  If you already have these software installed and accessible on your laptop, please skip to the bottom and run the checks.
  Otherwise there are installation instructions listed below.
</p>

<p>
  The Carpentries maintains a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "https://github.com/carpentries/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>


{% include setupNoR.html %}

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

  <br>
If theses checks work, then you are all set!   
 Otherwise, please follow the installation instructions above, and then try these tests again. Contact <a href='mailto:{{page.email}}'>{{page.email}}</a> if you are still having issues.
</p>
