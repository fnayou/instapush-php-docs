Requesting APIs
===============

`InstapushPHP`_ make it easy to request `Instapush.im`_ APIs.

.. note::
    Please check `Instapush REST documentation`_ for more information about REST APIs.

List of applications
--------------------

In order to get list of applications for given user, all you have to do ::

    use Fnayou\InstapushPHP\InstapushClient;

    // initiate Instapush client for User use
    $apiClient = InstapushClient::createForUser('user-token');

    // list of applications
    /** @var \Fnayou\InstapushPHP\Model\Applications $applications */
    $applications = $apiClient->applications()->list();

The response ``$applications`` will be instance of ``Fnayou\InstapushPHP\Model\Applications``
that extend ``Doctrine\Common\Collections\ArrayCollection``.

.. note::
    Full description of :doc:`Fnayou\\InstapushPHP\\Model\\Applications <models/applications>` model.

Add application
---------------

In order to add application for given user, all you have to do ::

    use Fnayou\InstapushPHP\InstapushClient;
    use Fnayou\InstapushPHP\Model\Application;

    // initiate Instapush client for User use
    $apiClient = InstapushClient::createForUser('user-token');

    // initiate new Application Model
    $newApplication = new Application('My New Application');

    // add the new application
    /** @var \Fnayou\InstapushPHP\Model\Application $application */
    $application = $apiClient->applications()->add($newApplication);

The response ``$application`` will be instance of ``Fnayou\InstapushPHP\Model\Application``.

.. note::
    Full description of :doc:`Fnayou\\InstapushPHP\\Model\\Application <models/application>` model.

List of events
--------------

In order to get list of events for given application, all you have to do ::

    use Fnayou\InstapushPHP\InstapushClient;

    // initiate Instapush client for App use
    $apiClient = InstapushClient::createForApp('app-id', 'app-secret');

    // list of events
    /** @var \Fnayou\InstapushPHP\Model\Events $events */
    $events = $apiClient->events()->list();

The response ``$events`` will be instance of ``Fnayou\InstapushPHP\Model\Events``
that extend ``Doctrine\Common\Collections\ArrayCollection``.

.. note::
    Full description of :doc:`Fnayou\\InstapushPHP\\Model\\Events <models/events>` model.

Add event
---------

In order to add event for given application, all you have to do ::

    use Fnayou\InstapushPHP\InstapushClient;
    use Fnayou\InstapushPHP\Model\Event;

    // initiate Instapush client for App use
    $apiClient = InstapushClient::createForApp('app-id', 'app-secret');

    // initiate new Event Model
    $newEvent = new Event(
        'event_exemple',
        'the {example_1} is pretty cool, more than the {example_2}',
        ['example_1', 'example_2']
    );

    // add the new event
    /** @var \Fnayou\InstapushPHP\Model\Event $event */
    $event = $apiClient->events()->add($newEvent);

The response ``$event`` will be instance of ``Fnayou\InstapushPHP\Model\Event``.

.. note::
    Full description of :doc:`Fnayou\\InstapushPHP\\Model\\Event <models/event>` model.

Post notification
-----------------

In order to post notification for given application, all you have to do ::

    use Fnayou\InstapushPHP\InstapushClient;
    use Fnayou\InstapushPHP\Model\Notification;

    // initiate Instapush client for App use
    $apiClient = InstapushClient::createForApp('app-id', 'app-secret');

    // initiate new Notification Model
    $notification = new Notification(
        'event_exemple',
        [
            'example_1' => 'Guzzle Client',
            'example_2' => 'cURL Client',
        ]
    );

    // post notification, response will be boolean `true` if success
    $response = $apiClient->notification()->post($notification);

The response will be ``boolean`` if success.

.. note::
    Full description of :doc:`Fnayou\\InstapushPHP\\Model\\Notification <models/notification>` model.

.. _InstapushPHP: https://github.com/fnayou/instapush-php
.. _instapush.im: http://instapush.im/
.. _Instapush REST documentation: https://instapush.im/developer/rest
