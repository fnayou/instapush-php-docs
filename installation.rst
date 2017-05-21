Installation
============

The installation process of the `InstapushPHP`_.

With Composer
--------------------

You can use `Composer`_ to install the last version of the library.

.. code-block:: bash

    $ composer require fnayou/instapush-php

Now, all you have to todo is to choose and install the **HTTP Client** you want to use.

.. note::

    Note that we implement `Discovery`_ feature, so if you already use a http client like **Guzzle** then no more actions are required

    Please, take some minutes to check `Client Section`_ of the `PHP-HTTP`_ documentation.

Use With cURL Client
--------------------

In order to use `cURL Client`_ all you have to do is :

.. code-block:: bash

    $ composer require fnayou/instapush-php
    $ composer require php-http/curl-client

Use With Guzzle 6 Adapter
-------------------------

In order to use `Guzzle 6 Adapter`_ all you have to do is :

.. code-block:: bash

    $ composer require fnayou/instapush-php
    $ composer require php-http/guzzle6-adapter


.. _Guzzle 6 Adapter: https://github.com/php-http/guzzle6-adapter
.. _cURL Client: https://github.com/php-http/curl-client
.. _InstapushPHP: https://github.com/fnayou/instapush-php
.. _Composer: https://getcomposer.org/
.. _Discovery: http://docs.php-http.org/en/latest/discovery.html
.. _Client Section: http://docs.php-http.org/en/latest/clients.html
.. _PHP-HTTP: http://docs.php-http.org/en/latest/index.html
