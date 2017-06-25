SQL Mode Switcher
=================

Switch the [SQL mode for MySQL](http://dev.mysql.com/doc/refman/5.5/en/server-sql-mode.html) servers early in Backdrop's boostrap process.

Created as a quick way to check compatibility with PostgreSQL queries without having to actually connect to a different database server.

This uses MySQL's SET SESSION, but it really needs SET GLOBAL to keep the variable through the entire pageload. **The GLOBAL option requires the web user to have SUPER permission, which isn't a good idea to give to a production server account.**

This really ought to save the standard setting to a global variable on `hook_boot()`, then reset it on hook_exit(). It doesn't do that either.

Available SQL modes for configuration are as follows:

* ANSI
* STRICT_TRANS_TABLES
* TRADITIONAL
* ALLOW_INVALID_DATES
* ANSI_QUOTES
* ERROR_FOR_DIVISION_BY_ZERO
* HIGH_NOT_PRECEDENCE
* IGNORE_SPACE
* NO_AUTO_CREATE_USER
* NO_AUTO_VALUE_ON_ZERO
* NO_BACKSLASH_ESCAPES
* NO_DIR_IN_CREATE
* NO_ENGINE_SUBSTITUTION
* NO_FIELD_OPTIONS
* NO_KEY_OPTIONS
* NO_TABLE_OPTIONS
* NO_UNSIGNED_SUBTRACTION
* NO_ZERO_DATE
* NO_ZERO_IN_DATE
* ONLY_FULL_GROUP_BY
* PAD_CHAR_TO_FULL_LENGTH
* PIPES_AS_CONCAT
* REAL_AS_FLOAT
* STRICT_ALL_TABLES
* DB2
* MAXDB
* MSSQL
* MYSQL323
* MYSQL40
* ORACLE
* POSTGRESQL

Current Maintainer
------------------

- None

Credits
-------

- Originally written for Drupal by David Norman (https://www.drupal.org/sandbox/deekayen/1207626)
- Ported to Backdrop by David Norman (https://github.com/deekayen)

License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.
