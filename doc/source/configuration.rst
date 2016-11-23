Configuration
=============

Covering the neomodel 'config' module and its variables.

Database url
------------

Set your connection details::

    config.DATABASE_URL = 'bolt://neo4j:neo4j@localhost:7687`

Disable automatic index and constraint creation
-----------------------------------------------

After a StructuredNode class definition neomodel installs the corresponding constraints and indexes at compile time.
This can be annoying when unit testing.

You can disable this feature by setting the follow var (prior to loading your class definitions::

    from neomodel import config
    config.AUTO_INSTALL_LABELS = False

If you wish to manually install a nodes indexes and constraints::

    from neomodel import install_labels
    install_labels(YourClass)

Disable Django signals integration
----------------------------------

This is enabled automatically should django be installed. Set `config.DJANGO_SIGNALS = False` to disable them.