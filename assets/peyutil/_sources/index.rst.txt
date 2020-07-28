**********************************************
:mod:`peyutil`: Python utilities for Open Tree
**********************************************

.. automodule:: peyutil

The package is organized into subpackages for ease of maintenance.
However, the public functions are imported into `peyutil.__init__.py`,
so users can ignore the subpackage structure.
The subpackage structure is retained in the documentation structure below
as an organizational aid.

See https://opentreeoflife.github.io/ for general information about the
Open Tree of Life project.

IO functions
============
Implemented in the  input_output subpackage.

.. autofunction:: download
.. autofunction:: expand_path
.. autofunction:: expand_to_abspath
.. autofunction:: open_for_group_write
.. autofunction:: parse_study_tree_list
.. autofunction:: pretty_dict_str
.. autofunction:: read_as_json
.. autofunction:: read_filepath
.. autofunction:: write_to_filepath
.. autofunction:: write_as_json
.. autofunction:: write_pretty_dict_str

String manipulations
====================
.. autofunction:: increment_slug
.. autofunction:: slugify
.. autofunction:: underscored2camel_case


Misc functions
==============
.. autofunction:: doi2url
.. autofunction:: reverse_dict

Newick Tree tokenization
========================
See https://evolution.genetics.washington.edu/phylip/newicktree.html

peyutil provides some utilities for breaking string input into Newick tokens
or (on a higher level) events that happen when parsing an Newick string.

.. autoclass:: NewickTokenType
    :members:

.. autoclass:: NewickTokenizer
    :members:

.. autoclass:: NewickEvents
    :members:

.. autoclass:: NewickEventFactory
    :members:

Python 2+3 compatability
========================
Because Open Tree uses Python 2 and Python 3, peyutil provides
some conditonal importing to make basic usage in client code work without
conditioning on python version:

  * `StringIO`: imported from `io` in py3 and `cStringIO` in py2
  * `UNICODE`: `str` in py3 and `unicode` in py2
  * `urlencode`: from `urllib.parse.urlencode` or `urllib.urlencode`
  * `primitive_string_types`: a tuple of primitive string types `(str,)` or `(str, unicode)`


.. autofunction:: is_int_type
.. autofunction:: is_str_type
.. autofunction:: get_utf_8_string_io_writer
.. autofunction:: flush_utf_8_writer


For internal use only
=====================
Several functions implemented here have drawbacks (e.g. lack of thread safety)
that make them unwise to use in general. They tend to be used in a few spots of
other Open Tree of Life code that is executed in contexts in which they are
known to be safe to use.

.. autofunction:: any_early_exit
.. autofunction:: get_unique_filepath
.. autofunction:: pretty_timestamp
.. autofunction:: propinquity_fn_to_study_tree

Utilities for writing tests
===========================

.. autofunction:: peyutil.test.support.helper.testing_read_json
.. autofunction:: peyutil.test.support.helper.testing_write_json
.. autofunction:: peyutil.test.support.helper.testing_through_json
.. autofunction:: peyutil.test.support.helper.testing_dict_eq
.. autofunction:: peyutil.test.support.helper.testing_conv_key_unicode_literal

.. autofunction:: peyutil.test.support.pathmap.get_test_path_mapper
.. autoclass:: peyutil.test.support.pathmap.PathMapForTests
    :members:

.. autoclass:: peyutil.test.support.struct_diff.DictDiff
    :members:

.. autoclass:: peyutil.test.support.struct_diff.ListDiff
    :members:

.. autoclass:: peyutil.test.support.struct_diff.ListEdit
    :members:

.. autoclass:: peyutil.test.support.struct_diff.ListAddition
    :members:

.. autoclass:: peyutil.test.support.struct_diff.ListElModification
    :members:

