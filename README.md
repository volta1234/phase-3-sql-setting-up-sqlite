# Intro to SQL

## Overview

We'll get started with SQL by installing and trying out SQLite.

## Objectives

1. Check to see if SQLite is installed on your computer via a terminal command
2. Install SQLite on your computer
3. Create and open a database file and table
4. End all SQL commands using proper semicolon notation
5. Exit out of SQLite using the .quit command

## Installing SQL

If you are using the Learn IDE, you don't need to install anything. We've already done this for you :)

### MacOS

If you are on OSX version 10.4 or greater, you probably already have SQLite
installed. Find out by opening up the terminal and running:

```bash
which sqlite3
```

if you get back

`/usr/bin/sqlite3`

Then you have a working version of sqlite3 already installed on your system.
Thanks Apple! Skip ahead to the 'Trying it out' section below!

If not, then there are a couple of ways you can install SQLite.

### MacOS Manual Installation Options

#### Install With Homebrew:

You can install SQLite using a package manager for your operating system. If you
are on Mac, Homebrew is the way to go. To install Homebrew run the following:

```bash
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
```

The script that runs will explain what it is doing, and pause before it does it.

After installing Homebrew, install SQLite with:

```bash
brew install sqlite
```

#### Install From Binary:

If Homebrew isn't working out for you, you can download one of the pre-compiled
binary packages available at the [downloads page](http://www.sqlite.org/download.html). Look for your operating system, download and install the appropriate binary.

> **Note:** If you are receiving an error when trying to install SQLite, make
> sure the Xcode Command-Line Tools have properly installed. Try running
> `xcode-select --install` to resolve this issue.

### WSL Manual Installation Instructions

Below are the steps for installing SQLite on the Windows Sub-system for Linux:

1. Open your WSL terminal
2. Update your Ubuntu packages: `sudo apt update`
3. Once the packages have updated, install SQLite3 with: `sudo apt install sqlite3`
4. Confirm installation and get the version number: `sqlite3 --version`

For additional information, check out [this article on getting started with databases in WSL][wsl]

[wsl]: https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database#install-sqlite

## Trying it out

Okay, let's make sure everything is up and running. In your terminal, type:

```bash
sqlite3 test_sqlite.db
```

This will create a new database file called test_sqlite.db and open it in the
sqlite prompt. You should see something like:

```bash
SQLite version 3.7.12 2013-03-19 12:42:02
Enter ".help" for instructions
sqlite>
```

You are now looking at the sqlite prompt and can now run SQL statements and
commands. Let's create a database table called "test_table":

```bash
sqlite> create table test_table(id);
```

This command creates the table inside the test_sqlite.db database file. To
verify that the table was created, run the following command:

```bash
sqlite> .tables
```

You should see the table listed. If you have the directory you're working in
open in your code editor, you should also see the database file in your file
tree.

To exit sqlite, type `.quit` at the sqlite prompt.

**Top-Tip:** All SQL statements that you write in your terminal, inside the
sqlite prompt, `sqlite>`, *must be terminated with a semi-colon `;`*. If you hit
`enter` without adding a semi-colon to the end of your line, you will be
trapped! Don't worry though, just add that `;` on the new line and hit `enter`
again. Note, however, that this does not apply to sqlite commands that begin
with a `.` such as `.quit` and `.tables`. These commands will *not work* if you
add the semi-colon.

## Resources

- [SQLite Documentation](http://www.sqlite.org/docs.html)
- [Homebrew](http://mxcl.github.com/homebrew/)
- [ZetCode sqlite3](http://zetcode.com/db/sqlite/)
