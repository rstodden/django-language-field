========================
django-language-field
========================

Language Field for Django apps. Includes all language choices from the IANA Language Subtag Registry.

Included is:

* ``LanguageField``, a model field
* ``LanguageField``, a form field (Not yet implemented)
* ``regenerate.py``, a script to parse the latest language list from IANA

Installation
============

::

    pip install django-language-field


Basic usage
===========

Add ``languages`` to the list of the installed apps in
your ``settings.py`` file::

    INSTALLED_APPS = [
        ...
        'languages',
        ...
    ]

Then, you can use it like any regular model field::

    from languages.fields import LanguageField

    class MyModel(models.Model):
        ..
        language = LanguageField()
        ..

Internally, LanguageField is based upon ``CharField`` and by default
represents the as a string.

As with ``CharField``'s, it is discouraged to use ``null=True`` use ``blank=True`` if you want to make it a non-required field.

Update
============


* ``languages.py``: Django 4.0 compatibility `from django.utils.translation import gettext_lazy as _`
* ``fields.py``: `Fix LanguageField incorrect super() call (Django 3.2 compatibility) <https://github.com/audiolion/django-language-field/pull/6>`_ and `Fix for Django 3.2 <https://github.com/wonderguide-com/django-language-field>`_
* ``regenerate.py``: `update to Python3 (urllib and no urllib2) <https://github.com/agenteAND/django-language-field>`_