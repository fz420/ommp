ommp
====

ommp

1. 关于依赖安装
psycopg2 安装时报错，解决方案
$ sudo apt install python-psycopg2
$ sudo apt install libpq-dev



.. image:: https://img.shields.io/badge/built%20with-Cookiecutter%20Django-ff69b4.svg

     :alt: Built with Cookiecutter Django
.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
     :target: https://github.com/ambv/black
     :alt: Black code style


:License: MIT


Settings
--------

Moved to settings_.

.. _settings: https://cookiecutter-django.readthedocs.io/en/latest/settings.html



2. 设置环境变量
export DATABASE_URL=postgres://lite:redhat@127.0.0.1:5432/testdb
export CELERY_BROKER_URL=redis://127.0.0.1:6379/0
export USE_DOCKER=false

在项目根目录下，建立 .env 文件，可以定义所有你需要的环境变量（需要在系统的环境变量DJANGO_READ_DOT_ENV_FILE=True）

Basic Commands
--------------


3. 初始化数据库
createdb testdb -U postgres --password your_password
python manage.py migrate

Setting Up Your Users
^^^^^^^^^^^^^^^^^^^^^

* To create a **normal user account**, just go to Sign Up and fill out the form. Once you submit it, you'll see a "Verify Your E-mail Address" page. Go to your console to see a simulated email verification message. Copy the link into your browser. Now the user's email should be verified and ready to go.

4. 建立管理员
* To create an **superuser account**, use this command::

    $ python manage.py createsuperuser

For convenience, you can keep your normal user logged in on Chrome and your superuser logged in on Firefox (or similar), so that you can see how the site behaves for both kinds of users.

5. 运行项目
python manane.py runserver ipadd:port

Type checks
^^^^^^^^^^^

Running type checks with mypy:

::

  $ mypy ommp

Test coverage
^^^^^^^^^^^^^

To run the tests, check your test coverage, and generate an HTML coverage report::

    $ coverage run -m pytest
    $ coverage html
    $ open htmlcov/index.html

Running tests with py.test
~~~~~~~~~~~~~~~~~~~~~~~~~~

::

  $ pytest

Live reloading and Sass CSS compilation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Moved to `Live reloading and SASS compilation`_.

.. _`Live reloading and SASS compilation`: http://cookiecutter-django.readthedocs.io/en/latest/live-reloading-and-sass-compilation.html



Celery
^^^^^^

This app comes with Celery.

To run a celery worker:

.. code-block:: bash

    cd ommp
    celery -A config.celery_app worker -l info

Please note: For Celery's import magic to work, it is important *where* the celery commands are run. If you are in the same folder with *manage.py*, you should be right.





Sentry
^^^^^^

Sentry is an error logging aggregator service. You can sign up for a free account at  https://sentry.io/signup/?code=cookiecutter  or download and host it yourself.
The system is setup with reasonable defaults, including 404 logging and integration with the WSGI application.

You must set the DSN url in production.


Deployment
----------

The following details how to deploy this application.



Docker
^^^^^^

See detailed `cookiecutter-django Docker documentation`_.

.. _`cookiecutter-django Docker documentation`: http://cookiecutter-django.readthedocs.io/en/latest/deployment-with-docker.html



