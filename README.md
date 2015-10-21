# Intro to SQL

## Objectives

1. Define SQL as a language for managing data in a database.
2. List three different relational database management systems.
3. Install SQL on your computer
4. Create and open a database file and table 

## Installing SQL

### Macs Make It Easy

If you are on OSX version 10.4 or greater, you probably already have SQLite installed. Find out by opening up the terminal and pasting in:

```bash
which sqlite3
```

if you get back

`/usr/bin/sqlite3`

Then you have a working version of sqlite3 already installed on your system. Thanks Apple! Skip ahead to the next lesson!

If not, then there are a couple of ways you can install SQLite.

### Manual Installation Options

#### Install With Homebrew:

Via a package manager for your operating system. If you are on Mac, homebrew is the way to go. You can install it by pasting:

```bash
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
```

into your terminal. The script that runs will explain what it is doing, and pause before it does it.

After installing homebrew, install sqlite with:

```bash
brew install sqlite
Install From Binary
```

If homebrew isn't working out for you, you can download one of the pre-compiled binary packages available at the [downloads page](http://www.sqlite.org/download.html). Look for your operating system, download and install the appropriate binary.

## Trying it out

Okay, let's make sure everything is up and running. In your terminal, type:

```bash
sqlite3 test_sqlite.db
```

This will open a new database file called test_sqlite.db and open it in the sqlite prompt. You should see something like:

```bash
SQLite version 3.7.12 2013-03-19 12:42:02
Enter ".help" for instructions
Enter SQL statements terminated with a ";"
sqlite>
```

You are now looking at the sqlite prompt.

Let's create a database table called "Test Table":

```bash
sqlite> create table test_table(id);
sqlite> .quit
```

You should have created a test_sqlite.db file. Either open up the directory you are working from in finder or type `open .` into your terminal. You should see that, inside whatever directory you've been working in, you have your `test_sqlite.db` file. 

**Top-Tip:** All SQL statements that you write in your terminal, inside the sqlite prompt, `sqlite3>`, *must be terminated with a semi-colon `;`*. If you hit `enter` without adding a semi-colon to the end of your line, you will be trapped! Don't worry though, just add that `;` on the new line and hit `enter` again. The only command that *doesn't* require, and in fact doesn't even work with, a `;` is the `.quit` command.

## Resources

- [SQLite Documentation](http://www.sqlite.org/docs.html)
- [Homebrew](http://mxcl.github.com/homebrew/)
- [ZetCode sqlite3](http://zetcode.com/db/sqlite/)

