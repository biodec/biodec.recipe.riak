A brief documentation
=====================

This recipe takes a number of options:

erlang-path
    The path where to find the erlc command (default = find it in your path).

url
    The URL to download the Riak source distribution.

prefix
    Prefix path (default = <buildout directory>).

cookie 
    Optional string passed as cookie to the erl runtime (-setcookie)

Tests
=====

We will define a buildout template used by the recipe:

    >>> buildout_cfg = """
    ... [buildout]
    ... parts = riak
    ... offline = true
    ...
    ... [riak]
    ... recipe = biodec.recipe.riak
    ... url = http://downloads.basho.com/riak/CURRENT/riak-1.1.4.tar.gz
    ... """

We'll start by creating a buildout:

    >>> import os.path
    >>> write('buildout.cfg', buildout_cfg)

Running the buildout gives us:

    >>> output = system(buildout)
    >>> if output.endswith("BBB TODO BBB\n"): True
    ... else: print output
    True
