=====
sauth
=====


.. image:: https://img.shields.io/pypi/v/sauth.svg
        :target: https://pypi.python.org/pypi/sauth

**S** erver **auth**

A simple server for serving directories via http or https and BASIC authorization::

    $ sauth --help
    usage: sauth [-h] [-u USERNAME] [-p PASSWORD] [--ip IP] [--port PORT] [-d DIR]
             [-s] [-t]

    A simple server for serving directories via http or https and BASIC authorization


    optional arguments:
    -h, --help            show this help message and exit
    -u USERNAME, --username USERNAME
                            Create a user who can access this server
    -p PASSWORD, --password PASSWORD
                            Create a password for the user
    --ip IP               Use a different IP address (Default: 0.0.0.0)
    --port PORT           Use a different Port (Default: 8333)
    -d DIR, --dir DIR     Use a different directory (Default: Current Directory)
    -s, --https           Use https
    -t, --use-threads     Serve each request in a different thread

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

    $ sauth -u someuser -p somepass
    Serving "/home/user/somedir" directory on http://0.0.0.0:8333

You can specify port and ip to serve on with `--port` and `--ip`::

    $ sauth -u someuser -p somepass --ip 127.0.0.1 --port 1234
    Serving "/home/user/somedir" directory on http://127.0.0.1:1234

Threading is also supported through  `-t` or `--use-threads` flags::

    $ sauth -u someuser -p somepass --ip 127.0.0.1 --port 1234 -t
    Serving "/home/user/somedir" directory on http://127.0.0.1:1234 using threading