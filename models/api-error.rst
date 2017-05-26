ApiError
========

``ApiError`` will be created and returned only if you set the ``handleException`` to ``false`` in your ``InstapushClient`` instance.

.. note::
    Please check :doc:`Handling Exception <../handling-exception>` documentation.

======= ====== ==================================
Field   Type   Description
======= ====== ==================================
status  string the http status of the API request
message string the message returnedby the API
======= ====== ==================================
