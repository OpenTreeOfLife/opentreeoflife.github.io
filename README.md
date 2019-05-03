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


### Update local Jekyll to match GitHub Pages server

We use the `github-pages` gem in our simple Gemfile to accurately reflect the
behavior on current GitHub Pages. This gem should accurately reflect
[the versions currently used by GitHub](https://pages.github.com/versions/).

To update your local environment, just run
`bundle update github-pages`.

If this requires a newer version of Ruby, this (assumes [RVM](https://rvm.io/)
is installed) will download a recent stable Ruby version and use it by default.
```sh
$ rvm use ruby --install --default
```

### Scheduled maintenance page

The page **maintenance.md** is designed for use during scheduled downtime for any Open Tree website(s). Edit its notice text, being careful to preserve the surrounding `DIV` elements and their assigned CSS classes. Then redirect to its URL (http://opentreeoflife.github.io/maintenance.html) from the intended webserver, using a **302 Temporary** response. Currently, the easiest way to do this is by [un-commenting this line](https://github.com/OpenTreeOfLife/opentree/blob/d35768d9a2233908a1982846870cf57326450525/deploy/setup/apache-config-shared#L15-L16) in our shared apache configuration file. This should be on the server as `/etc/apache2/opentree-config-shared`.


### Credits
Recently added (Apr 2019) site config based on code from https://github.com/barryclark/jekyll-now/
