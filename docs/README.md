[Documentation][freeseer-docs]
------------------------------

We use [Sphinx][] to generate the project's documentation.
Documentation is written in [reStructuredText][] and stored in `.rst` files.

We use [Read the Docs][] (RTD) for hosting. RTD uses a [web hook][] to build the
documentation whenever we push to this repository.

Getting started
---------------

1. Install Sphinx with `pip install -Ur requirements.txt`  
   If that doesn't work, try the [official instructions][install-sphinx]
2. Use the [reStructuredText Primer][rst-primer] as a reference

Autogenerated documentation from docstrings
-------------------------------------------

We have the ability to [include documentation from docstrings][autodoc].
For this to work, the docstrings must be written in correct reStructuredText.
You can then use all of the usual Sphinx markup in the docstrings and it will end
up correctly in the documentation.

Together with hand-written documentation, this technique eases the pain of
having to maintain two locations for documentation, while at the same time
avoiding auto-generated-looking pure API documentation.

We currently use this for plugins (see the userguide in the docs), and plan on
doing the same for more of our modules.

Build & preview your changes locally
------------------------------------

Once you've made your changes to the documentation, rebuild the HTML output.

    $ cd docs/
    $ make clean # Optional. Removes the build/ directory. Use if experiencing issues due to Sphinx's cache.
    $ make html

The updated HTML files will be in `docs/build/html/`.
There are two ways to view the built documentation locally:

- Open any of the HTML files in `docs/build/html/` with your web browser
- Or serve the contents of `docs/build/html/` from a local server  
  E.g. run `python -m SimpleHTTPServer` from `docs/build/html`
  and navigate your browser to `localhost:8000`

You can view the underlying reStructuredText of any page built with Sphinx by
clicking the "Show Source" link on such a page.

[freeseer-docs]: http://freeseer.readthedocs.org
[sphinx]: http://sphinx.pocoo.org
[restructuredtext]: http://docutils.sf.net/rst.html
[autodoc]: http://sphinx-doc.org/ext/autodoc.html
[install-sphinx]: http://sphinx-doc.org/latest/install.html
[rst-primer]: http://sphinx.pocoo.org/rest.html
[read the docs]: https://readthedocs.org/projects/freeseer/
[web hook]: http://read-the-docs.readthedocs.org/en/latest/webhooks.html