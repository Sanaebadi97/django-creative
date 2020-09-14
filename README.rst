=====
Django Creative
=====

**Modern template for Django admin interface**

Why Django Creative?
===============

* New fresh look
* Responsive mobile interface
* Useful admin home page
* Minimal template overriding
* Easy integration

Screenshots
===========

.. image:: https://creativetimblog.com/blog/wp-content/uploads/2019/08/Django-Template%E2%80%93-Black-Dashboard-730x410.png
    :alt: Screenshot #1
    :align: center
    :target: https://creativetimblog.com/blog/wp-content/uploads/2019/08/Django-Template%E2%80%93-Black-Dashboard-730x410.png

Installation
============

* Download and install latest version of Django Creative:

.. code:: python

    pip install django-creative
    # or
    easy_install django-creative

* Add 'creative' application to the INSTALLED_APPS setting of your Django project settings.py file (note it should be before 'django.contrib.admin'):

.. code:: python

    INSTALLED_APPS = (
        ...
        'creative',
        'django.contrib.admin',
    )

* Make sure ``django.template.context_processors.request`` context processor is enabled in settings.py (Django 1.8+ way):

.. code:: python

    TEMPLATES = [
        {
            'BACKEND': 'django.template.backends.django.DjangoTemplates',
            'DIRS': [],
            'APP_DIRS': True,
            'OPTIONS': {
                'context_processors': [
                    ...
                    'django.template.context_processors.request',
                    ...
                ],
            },
        },
    ]

.. warning::
    Before Django 1.8 you should specify context processors different way. Also use ``django.core.context_processors.request`` instead of ``django.template.context_processors.request``.

    .. code:: python

        from django.conf import global_settings

        TEMPLATE_CONTEXT_PROCESSORS = global_settings.TEMPLATE_CONTEXT_PROCESSORS + (
            'django.core.context_processors.request',
        )

* Create database tables:

.. code:: python

    python manage.py migrate creative
    # or 
    python manage.py syncdb
        
* Collect static if you are in production environment:

.. code:: python

        python manage.py collectstatic
        
* Clear your browser cache
