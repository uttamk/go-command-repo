A command repository for Go
===========================

Introduction
------------
A selection of snippets to get you started with various tools via Go's custom command. This Readme
describes syntax of a command and the structure of the repository. For more information about Go's
support for a command repository, please check

<http://www.thoughtworks-studios.com/docs/go/current/help/command_repository.html>

Caution: Please do not change/add anything under the default repo on the Go server. Refer the above
link for setting up your own command repository.

Version.txt
-----------
Go Server bundles a clone of the repository at <https://github.com/goteam/go-command-repo> by
default. The file version.txt is meant to allow conditional overwriting of the repository during
server upgrades.

Command Syntax
--------------
A valid command file looks like this:

    <exec command="curl">
      <arg>-u</arg>
      <arg>user:password</arg>
      <arg>http://targeturl</arg>
    </exec>

It must be a .xml file. The command attribute is mandatory. No other attributes are valid. Zero or more
arg child elements can be specified. No other child elements are allowed. One command file may only
contain one command.

Command Documentation
---------------------
Documentation is fully optional but it aids lookup and use if present. Here is the above command with
full documentation. Each item of documentation is key:value. Only whitespace characters may
precede a key. Value terminates with newline (no multi-line values). Each keyword may only contain
alphanumeric characters (no spaces, underscores etc), else it will be ignored for lookup. Name may
contain alphanumeric characters and spaces only.

**note:** author refers to author of the command xml file, not the underlying tool :-)

    <!--
      name: curl
      description: curl is a command line tool for transferring data with URL syntax
      keywords: curl, wget, download, httpclient
      moreinfo: http://curl.haxx.se/docs/manpage.html
      author: Go Team
      authorinfo: http://support.thoughtworks.com/categories/20002778-go-community-support
    -->
    <exec command="curl">
      <arg>-u</arg>
      <arg>user:password</arg>
      <arg>http://targeturl</arg>
    </exec>
