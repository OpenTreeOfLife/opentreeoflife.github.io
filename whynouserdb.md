---
layout: page
title: Why the Open Tree of Life doesn't maintain a database of users
permalink: /whynouserdb/
---


We are a community project, and it is important to give credit
to the people who did the scientific research and those who
curated our studies.
So, we require that curators of our
<a href="https://tree.opentreeoflife.org/curator/">curation app</a>
be authenticated users so that we can maintain a chain of 
provenance information for how studies make it into our
synthetic tree pipeline.

The most obvious solution would be to create a database of users
and require people to set up an account.
Instead of taking this route, the Open Tree project has opted to have 
users authenticate using a third party service (currently GitHub
authentication is the only service we support).
Why did we take this approach?

  1. We didn't want to try to position ourselves as some sort of crucial
  gate-keeper for belonging to a collaborative community of phylogenetic
  researchers. 

  2. We didn't want to have to worry about securely storing user data. In
   our current system we hold almost no user information, and users can 
   use a feature-rich user account management interface that some one else
   maintains.

  3. We want to make the project's efforts truly open.
  All input from users is pushed to publicly viewable location immediately.
  So, the developers of the Open Tree infrastructure do not have any private
  knowledge about the users.
  And community curation of phylogenetic knowledge is always shared with everyone.
  Specifically:
    <ul>
    	<li>We push user comments to our <a href="https://github.com/OpenTreeOfLife/feedback">feedback repository</a> as soon as they are saved.</li>
        <li>Curated studies are pushed to <a href="https://github.com/OpenTreeOfLife/phylesystem-1">https://github.com/OpenTreeOfLife/phylesystem-1</a> whenever a user saves a study.</li>
        <li>collections of trees go <a href="https://github.com/OpenTreeOfLife/collections-1">https://github.com/OpenTreeOfLife/collections-1</a> whenever they are edited.</li>
        <li>taxonomic amendments at <a href="https://github.com/OpenTreeOfLife/amendments-1">https://github.com/OpenTreeOfLife/amendments-1</a> when they are created.</li>
    </ul>
