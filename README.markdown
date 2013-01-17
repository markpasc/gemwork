# gemwork #

gemwork is a tool for creating Ruby gem workspaces. It also provides a script for easily shelling into and out of them, much like environments created by Python `virtualenv`, Perl `local::lib`, etc. (In fact, the `activate` script it generates is cribbed mostly from virtualenv for Python.)

gemwork differs from RVM and such tools in that it only creates a gem workspace, using the existing Ruby you have installed.

## Usage ##

    $ gemwork myenv
    $ source myenv/bin/activate
    (myenv)$ gem install rdiscount  # or whatever
    (myenv)$ gem list | grep rdiscount
    rdiscount (1.6.8)
    (myenv)$ rdiscount --help
    Usage: rdiscount [<file>...]
    Convert one or more Markdown files to HTML and write to standard output. With
    no <file> or when <file> is '-', read Markdown source text from standard input.
    (myenv)$ deactivate
    $ gem list | grep rdiscount
    $ rdiscount --help
    -bash: rdiscount: command not found
    $

## Requirements ##

* Go 1, for building

## Installation ##

1. Run `go get github.com/markpasc/gemwork` to install the `gemwork` tool into your Go tree or current workspace.

If you installed Go on the Mac using Homebrew, you'll need to `brew unlink go && brew link go` to make the `gemwork` command available.
