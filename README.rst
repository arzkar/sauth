=====
sauth
=====


.. image:: https://img.shields.io/pypi/v/sauth.svg
        :target: https://pypi.python.org/pypi/sauth

**S** erver **auth**

A simple server for serving directories via http or https and BASIC authorization::

    $ sauth --help
    Usage: sauth [OPTIONS] USERNAME PASSWORD [IP] [PORT]

      Start http server with basic authentication current directory.

    Options:
      -d, --dir TEXT  use different directory
      -s, --https     use https
      -t, --thread    serve each request in a different thread
      --help          Show this message and exit.

* Free software: GNU General Public License v3

Installation
------------

::

    pip install sauth

Also available on Arch User Repository if you're running arch::
    
    pacaur -S sauth

Usage
-----

To serve your current directory simply run::

    $ sauth someuser somepass
    Serving "/home/user/somedir" directory on http://0.0.0.0:8333

You can specify port and ip to serve on with 3rd and 4th arguments::

    $ sauth someuser somepass 127.0.0.1 1234
    Serving "/home/user/somedir" directory on http://127.0.0.1:1234

Threading is also supported through `-t` or `--thread` flags:

    $ sauth someuser somepass 127.0.0.1 1234 --thread
    Serving "/home/user/somedir" directory on http://127.0.0.1:1234 using threading