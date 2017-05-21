InstapushPHP: PHP wrapper for instapush.im
==========================================

.. image:: assets/images/instapush-php_120x114.png
    :align: right
    :width: 120px
    :alt: InstapushPHP Logo

.. image:: https://scrutinizer-ci.com/g/fnayou/instapush-php/badges/quality-score.png?b=master
   :target: https://scrutinizer-ci.com/g/fnayou/instapush-php/?branch=master
   :alt: Scrutinizer Code Quality

.. image:: https://insight.sensiolabs.com/projects/39930e9c-c9b3-49cd-8aa5-56ed52793ed1/mini.png
   :target: https://insight.sensiolabs.com/projects/39930e9c-c9b3-49cd-8aa5-56ed52793ed1
   :alt: SensioLabsInsight



`InstapushPHP`_ is full php wrapper for `instapush.im`_ APIs that use the wonderful `PHP-HTTP`_.

`instapush.im`_ uses a simple REST API to receive messages from your application and send them to devices running mobile clients.

`InstapushPHP`_ will make it easy to interact with theses APIs :

* Abstraction of the http client so you can use : Curl, Guzzle 5, Guzzle 6, etc.
* Abstraction of request and response.
* Auto transformation of response into Objects.
* Easy installation process using **composer**
* Respect of PSR recommendations from the `PHP-FIG`_.
* Code quality guaranteed
* And much more.

.. toctree::
    :hidden:

    InstapushPHP <self>
    Installation <installation>
    Usage <usage>
    Requesting APIs <requesting-apis>
    Handling Exception <handling-exception>

.. toctree::
    :hidden:
    :caption: Models

    Applications <models/applications>
    Application <models/application>
    Events <models/events>
    Event <models/event>
    Notification <models/notification>
    ApiError <models/api-error>

.. |clearfloat|  raw:: html

    <div style="clear:left"></div>

.. _InstapushPHP: https://github.com/fnayou/instapush-php
.. _instapush.im: http://instapush.im/
.. _PHP-HTTP: http://docs.php-http.org/en/latest/index.html
.. _PHP-FIG: http://www.php-fig.org/
