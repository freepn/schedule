schedule
========


.. image:: https://img.shields.io/github/license/freepn/schedule
    :target: https://github.com/freepn/schedule/blob/master/LICENSE

.. image:: https://img.shields.io/github/v/tag/freepn/schedule?color=green&include_prereleases&label=latest%20release
    :target: https://github.com/freepn/schedule/releases
    :alt: GitHub tag (latest SemVer pre-release)

.. image:: https://travis-ci.org/freepn/schedule.svg?branch=master
    :target: https://travis-ci.org/freepn/schedule

.. image:: https://img.shields.io/codecov/c/github/freepn/schedule
    :target: https://codecov.io/gh/freepn/schedule
    :alt: Codecov

.. image:: https://img.shields.io/codeclimate/maintainability/freepn/schedule
    :target: https://codeclimate.com/github/freepn/schedule


Python job scheduling for humans.

An in-process scheduler for periodic jobs that uses the builder pattern
for configuration. Schedule lets you run Python functions (or any other
callable) periodically at pre-determined intervals using a simple,
human-friendly syntax.

Inspired by `Adam Wiggins' <https://github.com/adamwiggins>`_ article `"Rethinking Cron" <https://adam.herokuapp.com/past/2010/4/13/rethinking_cron/>`_ and the `clockwork <https://github.com/Rykian/clockwork>`_ Ruby module.

Features
--------

- A simple to use API for scheduling jobs.
- Very lightweight and no external dependencies.
- Excellent test coverage.
- Tested on Python 2.7, 3.5, and 3.6

Usage
-----

.. code-block:: bash

    $ pip install schedule

.. code-block:: python

    import schedule
    import time

    def job():
        print("I'm working...")

    schedule.every(10).minutes.do(job)
    schedule.every().hour.do(job)
    schedule.every().day.at("10:30").do(job)
    schedule.every(5).to(10).minutes.do(job)
    schedule.every().monday.do(job)
    schedule.every().wednesday.at("13:15").do(job)
    schedule.every().minute.at(":17").do(job)

    while True:
        schedule.run_pending()
        time.sleep(1)

Documentation
-------------

Schedule's documentation lives at `schedule.readthedocs.io <https://schedule.readthedocs.io/>`_.

Please also check the FAQ there with common questions.


Meta
----

Daniel Bader - `@dbader_org <https://twitter.com/dbader_org>`_ - mail@dbader.org

Distributed under the MIT license. See `LICENSE.txt <https://github.com/dbader/schedule/blob/master/LICENSE.txt>`_ for more information.

https://github.com/dbader/schedule
