# Intro to SQL

## Objectives

1. Define SQL and understand what it is used for. 
2. Install SQL on your computer

## What is SQL?

SQL (Structured Query Language) is a language for managing data in a database. Unlike some other sorts of programming languages, it's only used for one thing: talking to databases. Thus, you might hear it referred to as a "special purpose" programming language, which is really not all that terribly important to understand beyond knowing that you won't be using SQL to write the next big web app, but you might write some to interact with the database that powers it.

Even though SQL really only has one purpose, it is used by many different database systems you might be familiar with (don't worry if you're not) such as MySQL, PostgreSQL, or the system we'll being using in this course: SQLite. All of these are relational database management systems. 

## Installation

### Macs Make It Easy

If you are on OSX version 10.4 or greater, you probably already have SQLite installed. Find out by opening up the terminal and pasting in:

```bash
which sqlite3
```

if you get back

`/usr/bin/sqlite3`

Then you have a working version of sqlite3 already installed on your system. Thanks Apple! Skip ahead to

If not, then there are a couple of ways you can install SQLite.

### Manual Installation Options

#### Install With Hombrew:

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
sqlite 3 test_sqlite.db
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

## Resources

- [SQLite Documentation](http://www.sqlite.org/docs.html)
- [Homebrew](http://mxcl.github.com/homebrew/)
- [ZetCode sqlite3](http://zetcode.com/db/sqlite/)

