# PythonResources
A list of curated (by me) Python resources. Follow me along my Python journey of discovery!

## Abstract

This is a list of Python language resources that I found useful.
This list covers mainly version 3.10, which at the time of this document
was the current stable release of Python.

## Documentation

### The main Python docs
- https://docs.python.org/3/

###  Find, install and publish Python packages with the Python Package Index
- [https://pypi.org](https://pypi.org)

### The Python Packaging  Authority
- [https://www.pypa.io/en/latest/](https://www.pypa.io/en/latest/)

From their webpage:

 The Python Packaging Authority (PyPA) is a working group that maintains a core set of software projects used in Python packaging.
The software developed through the PyPA is used to package, share, and install Python software and to interact with indexes of downloadable Python software such as  pypi.


##  Python tutorial videos

Python for Everyone. A 13 hour video from Dr. Chuck (Charles Severance, Ph.D., University of Michigan)

- https://www.youtube.com/watch?v=8DvywoWv6fI

The course website:
- https://www.py4e.com

## CS50P From Harvard

These videos are taught by David J. Malan from the very popular CS50 online course.

Historical note: When David himself took this course back in the day, it was taught by Brian Kernighan.

These videos were shot live. So, there a few glitches. As the CS50 team posts 
edit videos, I will update this list.

Note re: timecodes Where possible, for the multiple lectures we have inserted the start time for each lecture.
We have attempted to give a approximate 1 minute of fudge factor before the lecture start.
If you feel we have errored herein, please fork, fix and do a PR.

### Course web site

[https://cs50.harvard.edu/python/2022/](https://cs50.harvard.edu/python/2022/)

### CS50 YouTube channel

[https://www.youtube.com/c/cs50/videos](https://www.youtube.com/c/cs50/videos)

CS50P
- Lectures 0, 1 and 2
  - https://youtu.be/TJKnZ784bSI?t=461

  0: This  lecture covers Python's input/output, variables and strings, integers and floats</br>
  1: This lecture covers conditionals and control flow</br>
  2:  Looping</br>

- Lectures 3 and 4
  - https://youtu.be/hpxHkOG6Nyg?t=822
  
  3: Error handling and Exceptions</br>
  4: Libraries including Python's standard libraries</br>  (1:27)

- Lectures 5 and 6
  - https://youtu.be/awVVjpBzuaI?t=730

  5: Unit tests</br>
  6: File input output</br> (1:42)

- Lectures 7
  - https://youtu.be/ENSHLS5DW8A?t=1116

  7: Regular Expressions

- Lecture 8
  - [https://www.youtube.com/watch?v=Ez5TgiFQhHg](https://www.youtube.com/watch?v=Ez5TgiFQhHg)

  8: Object oriented programming

- Lecture 9
  - [https://www.youtube.com/watch?v=k83sNsEqXY4](https://www.youtube.com/watch?v=k83sNsEqXY4)

  9: Misc. Python features and wrap-up
    * Set data type
    * Globals and Constants
  * argument parsing
  * list, dictionarry unpacking with '*list', '**dict'
  * variadic functions with '*args, **kwargs'
  * list, dictionary comprehensions
  * generators

Note: I might have missed a few other topics in Lec 9.

### Additional material  in Lecture 9

The beginnig of the Lecture 9 video contains 2 additioonal mini-lectures

- Debugging
- Python style.
  * PEP 8
  * Linters like black.

## David Beazley videos from various PyCons

Modules and Packaging:
- [https://www.youtube.com/watch?v=bGYZEKstQuQ](https://www.youtube.com/watch?v=bGYZEKstQuQ)

Generators
- [https://www.youtube.com/watch?v=5-qadlG7tWo](https://www.youtube.com/watch?v=5-qadlG7tWo)

Python Meta programming
- [https://www.youtube.com/watch?v=sPiWg5jSoZI](https://www.youtube.com/watch?v=sPiWg5jSoZI)


### Corey Schaefer

These videos are bite-sized between 10-30 minutes long.

The complete Python playlist (143 videos)
- https://youtube.com/playlist?list=PL-osiE80TeTt2d9bfVyTiXJA-UTHn6WwU

A better way to manage Python Virtual Environments with PipEnv
- https://www.youtube.com/watch?v=zDYL22QNiWk

### Trey Hunter

List Comprehensions and generators
- https://www.youtube.com/watch?v=ei71YpmfRX4

List Comprehensions and generators from PyCon 2018
- https://www.youtube.com/watch?v=_6U1XoxyyBY


## Youtube channels

### MCoding : James Murphy
- [https://www.youtube.com/channel/UCaiL2GDNpLYH6Wokkk1VNcg](https://www.youtube.com/channel/UCaiL2GDNpLYH6Wokkk1VNcg)

### Michael Kennedy
- [https://www.youtube.com/channel/UCB2z8yryU2efaHA74MoDN8w](https://www.youtube.com/channel/UCB2z8yryU2efaHA74MoDN8w)

### Tech with Tim
- https://www.youtube.com/c/TechWithTim

### NetworkChuck

This guy drinks WAY too much coffee
- https://www.youtube.com/channel/UC9x0AN7BWHpCDHSm9NiJFJQ

### David Beazley
- https://www.youtube.com/channel/UCbNpPBMvCHr-TeJkkezog7Q

### Anthony Explains
- [https://www.youtube.com/channel/UC46xhU1EH7aywEgvA9syS3w](https://www.youtube.com/channel/UC46xhU1EH7aywEgvA9syS3w)

### Neural Nine
- [https://www.youtube.com/c/NeuralNine/featured](https://www.youtube.com/c/NeuralNine/featured)


## Books

### By David Beazley

- The Python Cookbook
- Python Distilled
- Python Essentials

Links on Amazon
- https://www.amazon.com/Books-David-Beazley/s?rh=n%3A283155%2Cp_27%3ADavid+Beazley

## Docker Image
You can build your own Docker image to contain the almost latest version of Python.
```bash
docker build -t my_python:3.10 - <<'eof'
FROM ubuntu:22.04
RUN DEBIAN_FRONTEND=noninteractive \
    apt-get update && \
    apt-get install -y python3-pip vim jq
COPY Dockerfile /
eof
```
Those commands create a Docker image with Python 3, an editor ( vim ), and a JSON query tool ( jq ).
For a more elaborate build file, see the [./docker/Dockerfile](./docker/Dockerfile).


To use the image, use Docker run to launch a container instance.
### Example #1 - Super simple
```bash
docker run --rm -it my_python:3.10 python3
```
This gets you into an interactive python3 session.  And when you exit ( Ctrl-D ), the container is removed.

### Example #2 - Daemon mode
```bash
docker run -d --name python3 my_python:3.10 sleep inf
docker exec -it python3 /bin/bash
# you can leave the container by typing `exit` and re-enter with the `docker exec ...` command
```
This launches the container as a service that you can exec into it, in this case, running a bash shell.

Stoping, re-starting, pausing, and unpausing the container
```bash
docker stop python3
docker start python3
docker pause python3
docker unpause python3
```
Once the container is stopped, you can remove the container
```bash
docker rm python3
```

### Example #3 - Mounted local folder
This is similar to the daemon example, but shares the current folder with the container.
```bash
docker run -d --name python3 -v "${PWD}":/tmp/python3 -w /tmp/python3 my_python:3.10 sleep inf
docker exec -it python3 /bin/bash
```
Your current directory in the container will automatically be /tmp/python3, which is shared with the local file system.

## Additional resources

### Python playlist on ComputerPhile

- [https://www.youtube.com/playlist?list=PLzH6n4zXuckoUWpzSEpQNW6I8rXIzyi8w](https://www.youtube.com/playlist?list=PLzH6n4zXuckoUWpzSEpQNW6I8rXIzyi8w)

The above playlist shows how to write a simple Pong-like game in PyGame.


The Python Wiki
- [https://wiki.python.org/moin/](https://wiki.python.org/moin/)


This site seems a bit stale. So, YMMV.



## Selected notes from Python docs

These are some links within docs.python.org that I have found useful.

### Errors and Exception

- [https://docs.python.org/3/tutorial/errors.html](https://docs.python.org/3/tutorial/errors.html)

## Package documentation

Note: The first 4 packages are installed in the supplied   [./docker/Dockerfile](./docker/Dockerfile).

### Sphinx : Document your Python code
- [https://www.sphinx-doc.org/en/master/](https://www.sphinx-doc.org/en/master/)

### Black : Lint/re-format your code
- [https://github.com/psf/black](https://github.com/psf/black)
Any color you want, as long as it is black. (Ford, Henery ???)

### mypy: Type check your code with Python type hints
- [https://mypy.readthedocs.io/en/stable/](https://mypy.readthedocs.io/en/stable/)

### pytest: Unit test your code
- [https://docs.pytest.org/en/7.1.x/](https://docs.pytest.org/en/7.1.x/)

