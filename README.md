Lilypad Prototype
=================

A CRUD webapp to store knowledge like Wikipedia, but organize and present it in a way that facilitates prerequisite-by-prerequisite learning.

Deployed on Heroku at 
[lilypad-proto.herokuapp.com](http://lilypad-proto.herokuapp.com).

Written in Clojure with the Compojure web framework.  HTML generated with Hiccup.  Content stored in a PostgreSQL database.

Database info
-------------

Table name: nodes

Fields:
* id, smallserial
* title, text
* prereq, smallint[]
* descr, text
* example, text
* comment, text

Generate an empty nodes table in:
* the Leiningen REPL
  `(sql/db-do-commands DB (sql/create-table-ddl TABLE_KEY [:id :smallserial] [:title :text] [:prereq "smallint[]"] [:descr :text] [:example :text] [:comm :text]))`
* or in psql
  `create table nodes (id smallserial, title text, prereq smallint[], descr text, example text, comm text);`

TODO 
----

1.  *Visualize the knowledge tree*.  I think Garrett already has something in mind for this.
2.  *Sort the text-based view of the tree*.  Alphabetically would be a good start.  We should think about indenting too.
3.  *Nest prerequisites*.  Adding a prereq should recursively add all the prereq's prereqs, too.
4.  *Show postreqs*.  Users should see what they'll be able to learn next.
5.  *Confirm node deletion*.  A popup window will probably require clojurescript, which I haven't looked into yet.
6.  *Document code*?  ;)
