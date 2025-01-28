Django Cryptography 5
=====================

**Note: This is a fork of the official `georgemarshall/django-cryptography`_ project,
which appears to have be abandoned.
The only change made in this fork that the patch that `fixes Django 5 compatiblity`_
has been applied and pushed to pypi as a new project.**

.. _georgemarshall/django-cryptography: https://github.com/georgemarshall/django-cryptography/
.. _fixes Django 5 compatiblity: https://github.com/georgemarshall/django-cryptography/issues/74

You can install the forked version from pypi with the following command:

.. code-block:: console

   pip install django-cryptography-5

The rest of this README is the original README from the official project.

Django Cryptography
===================

A set of primitives for easily encrypting data in Django, wrapping
the Python Cryptography_ library. Also provided is a drop in
replacement for Django's own cryptographic primitives, using
Cryptography_ as the backend provider.

Do not forget to read the documentation_.

.. START HIDDEN
.. image:: https://img.shields.io/github/workflow/status/georgemarshall/django-cryptography/CI/master
   :target: https://github.com/georgemarshall/django-cryptography/actions/workflows/main.yml
   :alt: GitHub Workflow Status (branch)
.. image:: https://img.shields.io/codecov/c/github/georgemarshall/django-cryptography/master
   :target: https://app.codecov.io/gh/georgemarshall/django-cryptography/branch/master
   :alt: Codecov branch
.. END HIDDEN

Cryptography by example
-----------------------

Using symmetrical encryption to store sensitive data in the database.
Wrap the desired model field with ``encrypt`` to easily
protect its contents.

.. code-block:: python

   from django.db import models

   from django_cryptography.fields import encrypt


   class MyModel(models.Model):
       name = models.CharField(max_length=50)
       sensitive_data = encrypt(models.CharField(max_length=50))

The data will now be automatically encrypted when saved to the
database.  ``encrypt`` uses an encryption that allows for
bi-directional data retrieval.

Requirements
------------

* Python_ (3.7, 3.8, 3.9, 3.10, 3.11)
* Cryptography_ (2.0+)
* Django_ (3.2, 4.1, 4.2)

Installation
------------

.. code-block:: console

   pip install django-cryptography

.. _Cryptography: https://cryptography.io/
.. _Django: https://www.djangoproject.com/
.. _Python: https://www.python.org/
.. _documentation: https://django-cryptography.readthedocs.io/en/latest/
