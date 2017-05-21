Usage
=====

`InstapushPHP`_ is easy and simple to use.

Initiate InstapushPHP Client
----------------------------

First of all if you are **already** using a http client like *curl* or *guzzle*,
then let `Discovery`_ feature make the magic and all you have to do is to initiate `InstapushPHP`_ and start requesting::

    use Fnayou\InstapushPHP\InstapushClient;

    // initiate Instapush client
    $apiClient = InstapushClient::create('user-token', 'app-id', 'app-secret');

    // continue requesting ...

if you want to define **http cURL client** ::

    use Fnayou\InstapushPHP\InstapushClient;
    use Http\Client\Curl\Client as CurlClient;

    $curlOptions = [
        CURLOPT_CONNECTTIMEOUT => 10,
        CURLOPT_SSL_VERIFYPEER => false,
    ];

    // initiate cURL client
    $curlClient = new CurlClient(null, null, $curlOptions);

    // initiate Instapush client
    $client = new InstapushClient($curlClient);
    $apiClient = $client::create('user-token', 'app-id', 'app-secret');

    // continue requesting ...

if you want to define **Guzzle client** ::

    use Fnayou\InstapushPHP\InstapushClient;
    use GuzzleHttp\Client as GuzzleClient;
    use Http\Adapter\Guzzle6\Client as GuzzleAdapter;

    $config = [
        'timeout' => 60.0,
        'allow_redirects' => true,
        'verify' => false,
    ];

    // initiate guzzle client
    $guzzleClient = new GuzzleClient($config);
    $guzzleAdapter = new GuzzleAdapter($guzzleClient);

    // initiate Instapush client
    $client = new InstapushClient($guzzleAdapter);
    $apiClient = $client::create('user-token', 'app-id', 'app-secret');

    // continue requesting ...

.. note::
    no matter what **http client** you will use, the request of APIs will be the same.

Type of instance
----------------

`InstapushPHP`_ provide 3 types of instance :

Instance to use Instapush applications API and it require only **UserToken**::

    use Fnayou\InstapushPHP\InstapushClient;

    // initiate Instapush client for User use
    $apiClient = InstapushClient::createForUser('user-token');

Instance to use Instapush events and notifications APIs and it require **AppId** and **AppSecret**::

    use Fnayou\InstapushPHP\InstapushClient;

    // initiate Instapush client for App use
    $apiClient = InstapushClient::createForApp('app-id', 'app-secret');

Instance to use full Instapush APIs but for specific user and specific application::

    use Fnayou\InstapushPHP\InstapushClient;

    // initiate Instapush client for both user and app use
    $apiClient = InstapushClient::create('user-token', 'app-id', 'app-secret');

.. note::
    Please check `Instapush REST documentation`_ for more information.

.. _InstapushPHP: https://github.com/fnayou/instapush-php
.. _Discovery: http://docs.php-http.org/en/latest/discovery.html
.. _Instapush REST documentation: https://instapush.im/developer/rest
