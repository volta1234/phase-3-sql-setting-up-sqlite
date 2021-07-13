# Setting up SQLite

## Learning Goals

- Check to see if SQLite is installed on your computer via a terminal command
- Install SQLite on your computer
- Create and open a database file and table
- End all SQL commands using proper semicolon notation
- Exit out of SQLite using the .quit command

## Introduction

In this lesson, we'll set up some of the tools you'll need for interacting with
a database using SQL. There is an example database included in this lesson,
`chinook.db`. This database is provided by SQLite as a way of demonstrating some
of the features of the SQLite application. If you try to view this file in your
text editor now, you won't be able to — this is a special SQLite database file,
and as such, it has all kinds of special encoding that makes it visible only
within a SQLite application. Not to worry! We'll soon see how to interact with
all the data in this file using a couple different tools.

## Installing SQLite

### Installing SQLite in OSX

If you are on OSX version 10.4 or greater, you probably already have SQLite
installed. Find out by opening up the terminal and running:

```sh
$ which sqlite3
/usr/bin/sqlite3
```

If you see the output above, you have a working version of sqlite3 already
installed on your system. Thanks Apple! Skip ahead to the 'SQLite VSCode
Extension' section below!

If not, then there are a couple of ways you can install SQLite.

#### OSX: Install With Homebrew

You can install SQLite using Homebrew, which your should have installed as part
of your Flatiron environment setup. Install SQLite with:

```bash
brew install sqlite
```

#### OSX: Install From Binary

If Homebrew isn't working out for you, you can download one of the pre-compiled
binary packages available at the
[downloads page](http://www.sqlite.org/download.html). Look for your operating
system, download and install the appropriate binary.

> **Note:** If you are receiving an error when trying to install SQLite, make
> sure the Xcode Command-Line Tools have properly installed. Try running
> `xcode-select --install` to resolve this issue.

### Installing SQLite in WSL

Below are the steps for installing SQLite on the Windows Sub-system for Linux:

1. Open your WSL terminal
2. Update your Ubuntu packages: `sudo apt update`
3. Once the packages have updated, install SQLite3 with: `sudo apt install sqlite3`
4. Confirm installation and get the version number: `sqlite3 --version`

For additional information, check out [this article on getting started with databases in WSL][wsl]

[wsl]: https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database#install-sqlite

## SQLite VSCode Extension

To make it easier to interact with SQLite databases from VSCode, you should also
install the [SQLite VSCode Extension][sqlite vscode].

This will give you a graphical interface where you can interact with SQLite
databases without leaving VSCode! It's a great way to help visualize what's
happening with your database while you familiarize yourself with SQL syntax.

## DB Browser for SQLite

The last, and most comprehensive, graphical tool for interacting with SQLite
databases is DB Browser for SQLite. It's a separate, standalone graphical user
interface (GUI) application that has many features for exploring and interacting
with SQL databases.

To install it, head to the downloads page, and download the installer for your
operating system:

- [https://sqlitebrowser.org/dl/](https://sqlitebrowser.org/dl/)

For WSL users, you should download the Windows installer, not the Linux one.

## Trying It Out

Okay, let's make sure everything is up and running. We'll show how to explore a
database using both SQLite in the terminal as well as the VSCode extension.

### Using SQLite in the Terminal

In your terminal, type:

```bash
sqlite3 chinook.db
```

This will open the `chinook.rb` file in the SQLite prompt. You should see
something like:

```bash
SQLite version 3.7.12 2013-03-19 12:42:02
Enter ".help" for instructions
sqlite>
```

You are now looking at the SQLite prompt and can now run SQL statements and
commands. Let's explore the data from one of the tables in this database:

```bash
sqlite> SELECT * FROM artists;
```

This command retrieves all the data from the `artists` table inside the
`chinook.db` database file:

```txt
1|AC/DC
2|Accept
3|Aerosmith
4|Alanis Morissette
...
```

We'll talk more about the `SELECT` syntax in coming lessons. You can also view a
list of all the tables:

```bash
sqlite> .tables
```

You should see the table listed:

```txt
albums          employees       invoices        playlists
artists         genres          media_types     tracks
customers       invoice_items   playlist_track
```

To exit sqlite, type `.quit` at the sqlite prompt.

**Top-Tip:** All SQL statements that you write in your terminal, inside the
sqlite prompt, `sqlite>`, _must be terminated with a semi-colon `;`_. If you hit
`enter` without adding a semi-colon to the end of your line, you will be
trapped! Don't worry though, just add that `;` on the new line and hit `enter`
again. Note, however, that this does not apply to sqlite commands that begin
with a `.` such as `.quit` and `.tables`. These commands will _not work_ if you
add the semi-colon.

### Using the SQLite VSCode Extension

While it's nice to be able to interact with a SQL database directly from the
terminal, it's even nicer to be able to have a visual representation of what the
tables look like in a graphical user interface (GUI). One such GUI that we can
use without even leaving our text editor is the
[SQLite VSCode Extension][sqlite vscode].

To use it, first right-click on the `chinook.db` file, then select "Open database":

![Opening a database in SQLite Extension]()

This will create a new "SQLITE EXPLORER" menu within VSCode, below the file tree:

![Locating the SQLite Explorer in VSCode]()

Clicking the play button () next to any of the tables will open a new tab in
VSCode where you can see an output of all the rows in that table in a
spreadsheet-like format:

![Viewing tables in SQLite Extension]()

### Using DB Browser for SQLite

#### DB Browser in OSX

First, open the DB Browser for SQLite application:

![Open DB Browser in OSX]()

Then, select "Open Database":

![Open database in DB Browser in OSX]()

Finally, navigate to the directory where you cloned this lesson, and select the
`chinook.db` file:

![Open chinook.db file in DB Browser in OSX]()

#### DB Browser in WSL

First, open the DB Browser for SQLite application:

![Open DB Browser in WSL]()

Then, select "Open Database":

![Open database in DB Browser in WSL]()

Finally, navigate to the directory where you cloned this lesson, and select the
`chinook.db` file:

![Open chinook.db file in DB Browser in WSL]()

#### Exploring the Database

tk

## Resources

- [SQLite Documentation](http://www.sqlite.org/docs.html)
- [SQLite VSCode Extension][sqlite vscode]
- [ZetCode sqlite3 Tutorial](http://zetcode.com/db/sqlite/)

[sqlite vscode]: https://marketplace.visualstudio.com/items?itemName=alexcvzz.vscode-sqlite
