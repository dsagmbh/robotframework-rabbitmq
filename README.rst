RobotFramework RabbitMQ
=======================

|Build Status|

Short Description
-----------------

`Robot Framework`_ library for for working with RabbitMQ.

Installation
------------

Install the library from GitHub using pip:

::

    pip install "git+https://github.com/Quadrob/robotframework-rabbitmq.git"

Documentation
-------------

See keyword documentation for RabbitMQ library on `GitHub`_.

Example Code
------------

.. code:: robotframework

    *** Settings ***
    Library    RabbitMq
    Library    Collections

    Suite Setup         Create Rabbitmq Connection    my_host_name    15672    5773    guest    guest    alias=rmq    vhost=/    pathPrefix=my_prefix
    Suite Teardown      Close All Rabbitmq Connections

    *** Test Cases ***
    Check RabbitMQ Broker Connection is Active
        ${live}=	Is Alive
        Should Be True	${live}

    Check RabbitMQ Broker Details Overview
        ${overview}=    Overview
        Log Dictionary    ${overview}

License
-------

Apache License 2.0

.. _Robot Framework: http://www.robotframework.org
.. _GitHub: https://rawgit.com/peterservice-rnd/robotframework-rabbitmq/master/docs/RabbitMq.html

.. |Build Status| image:: https://travis-ci.org/peterservice-rnd/robotframework-rabbitmq.svg?branch=master
   :target: https://travis-ci.org/peterservice-rnd/robotframework-rabbitmq