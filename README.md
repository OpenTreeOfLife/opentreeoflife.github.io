opentreeoflife.github.io
========================

Page that describes the many repos on the OpenTree GutHub organization.


### Testing edits locally (using a cloned repo and your browser)

Built with [Jekyll](http://jekyllrb.com/). Run 

	$ bundle exec jekyll serve

to build locally and preview in your browser. 

Other useful options are `--port` and `--watch` (rebuilds the test site in response to local edits):

	$ bundle exec jekyll serve  --port 4001  --watch

With these settings, the site will be available at **http://localhost:4001/**


### Scheduled maintenance page

The page 'maintenance.md' is designed for use during scheduled downtime for any Open Tree website(s). Edit its notice text, being careful to preserve the surrounding `DIV` elements and their assigned CSS classes. Then redirect to its URL (http://opentreeoflife.github.io/maintenance.html) from the intended webserver, using a **302 Temporary** response.
