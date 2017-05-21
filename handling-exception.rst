Handling Exception
==================

`InstapushPHP`_ can handle exception/error in 2 different ways.

The method ``setHandleException`` specify if you want to throw an ``ApiException`` or to return ``ApiError`` model::

    use Fnayou\InstapushPHP\Exception\ApiException;
    use Fnayou\InstapushPHP\InstapushClient;

    // initiate Instapush client
    // handling is set to true by default so it will throw an `ApiException`
    $apiClient = InstapushClient::createForUser('user-token');

    // if you want to get `ApiError` instead
    $apiClient->setHandleException(false);


ApiException
------------

``ApiException`` extend from ``Http\Client\Exception\HttpException`` so you can access **Request** and **Response** objects::

    use Fnayou\InstapushPHP\Exception\ApiException;
    use Fnayou\InstapushPHP\InstapushClient;

    // initiate Instapush client
    $apiClient = InstapushClient::createForUser('user-token');

    try {
        /** @var \Fnayou\InstapushPHP\Model\Applications $applications */
        $applications = $apiClient->applications()->list();
    } catch (ApiException $apiException) {
        /** @var \Psr\Http\Message\RequestInterface $request */
        $request = $apiException->getRequest();

        /** @var \Psr\Http\Message\ResponseInterface $response */
        $response = $apiException->getResponse();
    }

ApiError
--------

if handling exception is turned off then you will get and ``ApiError`` object::

    use Fnayou\InstapushPHP\InstapushClient;
    use Fnayou\InstapushPHP\Model\ApiError;

    // initiate Instapush client
    $apiClient = InstapushClient::createForUser('user-token');
    $apiClient->setHandleException(false);

    $applications = $apiClient->applications()->list();

    if ($applications instanceof ApiError) {
        /** @var \Fnayou\InstapushPHP\Model\ApiError */
        $apiError = $applications;

        var_dump($apiError->getMessage());
        var_dump($apiError->getStatus());
    }

.. note::
    Full description of :doc:`Fnayou\\InstapushPHP\\Model\\ApiError <models/api-error>` model.

.. _InstapushPHP: https://github.com/fnayou/instapush-php
