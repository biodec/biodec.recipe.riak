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
    ... parts = riakbuild
    ... offline = true
    ...
    ... [riakbuild]
    ... recipe = biodec.recipe.riak:build
    ... url = http://downloads.basho.com/riak/CURRENT/riak-1.1.4.tar.gz
    ...
    ... """

We'll start by creating a buildout:

    >>> import os.path
    >>> write('buildout.cfg', buildout_cfg)

Running the buildout gives us:

    >>> print system(buildout)
    Installing riakbuild.
    ...
    ==> rel (compile)
    ==> riakbuild (compile)
    Compiled src/etop_txt.erl
    ...

