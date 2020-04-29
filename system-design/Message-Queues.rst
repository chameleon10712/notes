Message Queues
================

Message queues receive, hold, and deliver messages. If an operation is too slow to perform inline, you can use a message queue with the following workflow:

- An application publishes a job to the queue, then notifies the user of job status
- A worker picks up the job from the queue, processes it, then signals the job is complete

The user is not blocked and the job is processed in the background. During this time, the client might optionally do a small amount of processing to make it seem like the task has completed. For example, if posting a tweet, the tweet could be instantly posted to your timeline, but it could take some time before your tweet is actually delivered to all of your followers.

`Redis <https://redis.io/>`_ is useful as a simple message broker but messages can be lost.

`RabbitMQ <https://www.rabbitmq.com/>`_ is popular but requires you to adapt to the 'AMQP' protocol and manage your own nodes.

`Amazon SQS <https://aws.amazon.com/tw/sqs/>`_ is hosted but can have high latency and has the possibility of messages being delivered twice.


|

Task queues
==============

Tasks queues receive tasks and their related data, runs them, then delivers their results. They can support scheduling and can be used to run computationally-intensive jobs in the background.

`Celery <http://www.celeryproject.org/>`_ has support for scheduling and primarily has python support.

|

`[ref] <https://github.com/donnemartin/system-design-primer#cap-theorem>`_
