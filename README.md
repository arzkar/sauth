# sauth

**S**erver **auth**

A fork of [Granitosaurus's sauth](https://github.com/Granitosaurus/sauth) without the [Click](https://github.com/pallets/click) dependency, replaced with argparse.

Licensed under GNU General Public License v3

# Installation

## Download

There are many ways to download the script:

- Using [git](https://git-scm.com/downloads):

```
git clone https://github.com/arzkar/sauth
```

- Using [Wget](https://www.gnu.org/software/wget/):

```
wget https://raw.githubusercontent.com/arzkar/sauth/master/sauth.py
```

- Using [curl](https://curl.se/):

```
curl -O https://raw.githubusercontent.com/arzkar/sauth/master/sauth.py
```

- From within the browser:
  - Go to this [page](https://raw.githubusercontent.com/arzkar/sauth/master/sauth.py)
  - Right Click and save the file using "Save Page as"
  - Make sure that the filename is `sauth.py`, not `.txt`

## Run

```

python3 sauth.py

```

## Usage

```
> python3 sauth.py
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
```

## Examples

- To serve your current directory simply run::

```
    $ python3 sauth.py -u someuser -p somepass
    Serving "/home/user/somedir" directory on http://0.0.0.0:8333
```

- You can specify port and ip to serve on with `--port` and `--ip`::

```
    $ python3 sauth.py -u someuser -p somepass --ip 127.0.0.1 --port 1234
    Serving "/home/user/somedir" directory on http://127.0.0.1:1234
```

- Threading is also supported through `-t` or `--use-threads` flags:

```
    $ python3 sauth.py -u someuser -p somepass --ip 127.0.0.1 --port 1234 -t
    Serving "/home/user/somedir" directory on http://127.0.0.1:1234 using threading
```
