## Django proxy storage

Django proxy storage allows you to create proxy for storages.

Full documentation for project is available at http://chibisov.github.io/django-proxy-storage/docs

[![Build Status](https://travis-ci.org/chibisov/django-proxy-storage.png?branch=master)](https://travis-ci.org/chibisov/django-proxy-storage)
[![Latest Version](https://pypip.in/version/django-proxy-storage/badge.png)](https://pypi.python.org/pypi/django-proxy-storage/)


## Requirements

* Tested for python 2.7 and 3.4 versions
* Tested for Django 1.5.5, 1.6.5 and 1.7

## Running tests

Unittest of this package requires docker. That's why for Mac OS X you have to install [vagrant](http://www.vagrantup.com/downloads.html)
and only then run tests in VM.

    $ cd tests_app
    $ vagrant up
    $ vagrant ssh
    $ cd /vagrant/

Running the tests:

    $ sudo make prepare_for_tests
    $ tox -- tests_app

Running test for exact environment:

    $ tox -e django1.5.5 -- tests_app

Recreate envs before running tests:

    $ tox --recreate -- tests_app

Pass custom arguments:

    $ tox -- tests_app --verbosity=3

Run with pdb support:

    $ tox -- tests_app --processes=0 --nocapture

Run exact TestCase:

    $ tox -- tests_app.tests.unit.meta_backends.orm.tests:ORMMetaBackendTest

Run tests from exact module:

    $ tox -- tests_app.tests.unit.meta_backends.tests

## Documentation

Build docs:

    $ make build_docs

Automatically build docs by watching changes:

    $ pip install watchdog
    $ make watch_docs