BBEdit codeless language module for TaskPaper
=============================================

Matthias Steffens <mat@extracts.de>, and Dennis Rande
Version 1.1, 03-Nov-2007


Introduction
------------

From the TaskPaper website (<http://hogbaysoftware.com/products/taskpaper>):

  "TaskPaper is a simple to-do list application that helps you stay organized.
   Unlike competing applications, TaskPaper is based on plain text files which
   offer you paper-like simplicity and ease of use." 

TaskPaper is a to-do list application for Mac OS X based on the "Getting Things
Done" approach of David Allen (<http://www.davidco.com/>). It supports the GTD
notions of projects, tasks and contexts.

This package contains a BBEdit codeless language module for the simple to-do
list format used by TaskPaper. It is intended for Mac users who want to edit
their TaskPaper lists in BBEdit from time to time and for anyone who is looking
for a simple to-do list format. The language module will also work with
TextWrangler, the "lite" version of BBEdit.


Installation
------------

To install, copy the file 'TaskPaper.plist' to:
	
 ~/Library/Application Support/BBEdit/Language Modules/
	
and relaunch BBEdit. To install for use with TextWrangler, copy here:

 ~/Library/Application Support/TextWrangler/Language Modules/
	
and relaunch TextWrangler.

To color TaskPaper project names as keywords, add their names to the
BBLMKeywordList in file 'TaskPaper.plist'.


Syntax
------

The language module provides automatic color highlighting for task contexts
(tags) and notes. Project headings can be colored when explicitly specified in
the language module. Project headings and tasks can be indented with tabs for
grouping.

A task is a line that begins with a hyphen followed by a space ('- ') which can
optionally be prefixed (i.e. indented) with tabs or spaces. A task can have zero
or more context tags. Examples:

- this is a task
	- this is a sub-task with a @tag
- this task has two tags @done @work

A project heading is a line that isn't a task and ends with a colon (':').
Example:

this is a project heading:

Projects appear in BBEdit's function popup menu, and projects with several tasks
can be folded using BBEdit's fold methods.

A context tag has the form "@tag", i.e. it starts with an "at" character ("@"),
followed by a run of non-whitespace characters. A context tag can optionally
have a value assigned to it. The value syntax immediately follows the tag word
(no whitespace between) and is enclosed by '(' and ')'. The value text inside
can have whitespace, but no newlines. Examples:

@email
@priority(1)
@due(2007-11-02 23:00)

A note is any line that doesn't match the project or task rules.

More information about the TaskPaper file format is available at:
<http://hogbaysoftware.com/products/taskpaper/pages/file_format>


File-type Detection
-------------------

By default, the language module is applied to files with the .taskpaper, .todo,
.todos, .todolist, .task and .tasks extensions.


Requirements
------------

Requires BBEdit 8.5 (or higher), or, alternatively, TextWrangler 2.2 (or higher).
<http://www.barebones.com/products/bbedit/>
<http://www.barebones.com/products/textwrangler/>


Licence
-------

Copyright (C) 2007 by Matthias Steffens <mat@extracts.de>

Released under a Creative Commons Attribution-ShareAlike License:
<http://www.creativecommons.org/licenses/by-sa/3.0/>


Acknowledgements
----------------

Thanks to Dennis Rande for improving the initial version. The initial version
was based on templates and hints by Seth Dillingham, available at:
<http://www.truerwords.net/articles/bbedit/codeless_language_module.html>


Contact
-------

The authors of this BBEdit codeless language module are Matthias Steffens
<mat@extracts.de> and Dennis Rande.

For all information regarding the TaskPaper application itself please visit
<http://hogbaysoftware.com/products/taskpaper/>.


Version History
---------------

  Version 1.1 (02-Nov-2007)
---------------------------
- added 'BBLMCanSpellCheckCodeRuns' property
- improved regular expression for 'String Pattern' to account for tags with
  values (like "@tag(value)")
- added more characters to the 'Identifier and Keyword Character Class' property
Changes by Dennis Rande:
- added several new keywords for project names
- changed value of 'BBLMIsCaseSensitive' property from 'true' to 'false'
- shortened value of 'BBLMLanguageDisplayName' property to 'TaskPaper'
- added a few extra language suffixes
- wrapped regular expressions as CDATA for improved legibility
- improved syntax checking of TaskPaper notes

  Version 1.0 (29-Oct-2007)
---------------------------
- initial version
