# Introduction #

Opcit is a python application using QT as its GUI library and either postgres or sqlite as the backend database. It does not have any fancy install script yet, so the installation process is largely manual.


# Prerequisites #

  * Qt 4.x: A C++ GUI library which runs natively on Linux/Unix, Mac OS 10, and Windows. You can find it here: http://www.trolltech.com/products/qt/downloads
  * PyQt: Python bindings to Qt. Find them here http://www.riverbankcomputing.co.uk/pyqt/
  * bibutils (optional): a set of tools to convert bibliography formats between the library of congress' MODS XML format and back. Includes ISI, bibtex, etc. Only needed for importing an exporting of references. Find it here: http://www.scripps.edu/~cdputnam/software/bibutils/
  * PyXML (optional): newer version of the XML suite for python - appears to come installed by default with most linux distros, needed to be installed on OS X. Only used for XML exports. Find it here: http://pyxml.sourceforge.net/
  * sqlite or postgresql: opcit works with either database at this point. Sqlite is much simpler to install and administer and can be found here http://www.sqlite.org/, whereas postgresql provides more advanced features, and can be found here: http://www.postgresql.org/ Note that if using postgres then the QPSQL drivers have to be compiled when compiling QT 4.x
  * Biopython (optional): used to retrieve PubMed records. Find it here: http://biopython.org

# Step 1: get the source code #

The source code only lives in the google-code subversion repository. Go to http://code.google.com/p/opcit and look at the svn tab for instructions for checking it out.

# Step 2: set up the database #

Once all the prerequisites are installed, the database has to be set up. The database schema is contained in a file called _base.sql_. To set up a database using sqlite, do the following:

```
$ sqlite3 file-to-contain-database
sqlite> .read base.sql
```

# Step 3: test the setup #

Run the test-suite:

```
$ python unittest_bibitem.py
```

Lots of output should be spewed across the screen. If all goes well the final message should be "OK".