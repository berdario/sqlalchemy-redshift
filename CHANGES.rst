0.3.2 (unreleased)
------------------

- Change the name of the package to `sqlalchemy_redshift` to match the naming
  convention for other dialects; the `redshift_sqlalchemy` package now emits
  a `DeprecationWarning` and references `sqlalchemy_redshift`.
  The `redshift_sqlalchemy` compatibility package will be removed
  in a future release.
  (`Issue #58 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/58>`_)


0.3.1 (2015-10-08)
------------------

- Fix breakages to CopyCommand introduced in 0.3.0:
  Thanks `solackerman <https://github.com/solackerman>`_.
  (`Issue #53 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/53>`_)

  - When `format` is omitted, no `FORMAT AS ...` is appended to the query. This
    makes the default the same as a normal redshift query.
  - fix STATUPDATE as a COPY parameter


0.3.0 (2015-09-29)
------------------

- Fix view support to be more in line with SQLAlchemy standards.
  `get_view_definition` output no longer includes a trailing semicolon and
  views no longer raise an exception when reflected as `Table` objects.
  (`Issue #46 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/46>`_)
- Rename RedShiftDDLCompiler to RedshiftDDLCompiler.
  (`Issue #43 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/43>`_)
- Update commands
  (`Issue #52 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/52>`_)

  - Expose optional TRUNCATECOLUMNS in CopyCommand.
  - Add all other COPY parameters to CopyCommand.
  - Move commands to their own module.
  - Support inserts into ordered columns in CopyCommand.


0.2.0 (2015-09-04)
------------------

- Use SYSDATE instead of NOW().
  Thanks `bouk <https://github.com/bouk>`_.
  (`Issue #15 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/15>`_)
- Default to SSL with hardcoded AWS Redshift CA.
  (`Issue #20 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/20>`_)
- Refactor of CopyCommand including support for specifying format and
  compression type. (`Issue #21 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/21>`_)
- Explicitly require SQLAlchemy >= 0.9.2 for 'dialect_options'.
  (`Issue #13 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/13>`_)
- Refactor of UnloadFromSelect including support for specifying all documented
  redshift options.
  (`Issue #27 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/27>`_)
- Fix unicode issue with SORTKEY on python 2.
  (`Issue #34 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/34>`_)
- Add support for Redshift ``DELETE`` statements that refer other tables in
  the ``WHERE`` clause.
  Thanks `haleemur <https://github.com/haleemur>`_.
  (`Issue #35 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/35>`_)
- Raise ``NoSuchTableError`` when trying to reflect a table that doesn't exist.
  (`Issue #38 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/issues/38>`_)

0.1.2 (2015-08-11)
------------------

- Register postgresql.visit_rename_table for redshift's
  alembic RenameTable.
  Thanks `bouk <https://github.com/bouk>`_.
  (`Issue #7 <https://github.com/sqlalchemy-redshift/sqlalchemy-redshift/pull/7>`_)


0.1.1 (2015-05-20)
------------------

- Register RedshiftImpl as an alembic 3rd party dialect.


0.1.0 (2015-05-11)
------------------

- First version of sqlalchemy-redshift that can be installed from PyPI
