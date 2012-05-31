########
Workflow
########


This is the documentation of general guide lines, standards, recommendations and
strategies used for the development of web projects. This also covers the code
management, work environments setup, development/release cycle, deployment,
packaging, documenting, django specific project structure, git version
control , git workflows and code hosting.


Development environment
=======================
**Eclipse pydev as IDE**

Eclipse plugins used:

- Rest plugin
- Egit

Python prerequisites:

- python>=2.6<3.0
- Django==1.4
- sphinx
- virtualenv
- pip


Eclipse-Project Guide-Lines
---------------------------

- Create virtual environment for each project

Pydev project structure
-----------------------

Project structure is as follows.

::
    
    |--PydevProject
       |--docs
       |--mydjangoproject
       |  |--__init__.py
       |  |--settings.py
       |  |--urls.py
       |  |--wsgi.py
       |--myapp
       |--thirdpartymodulecustomized1    #included as git submodules 
       |--thirdpartyappcustomized1       #included as git submodules
       |--tests
       |--README.rst
       |--.gitignore
       |--manage.py

- all the apps are decoupled from Django-project. If possible try to make apps
  generalized i.e usable in other projects. in later case maintain separate
  project for app (see `django general purpose app structure`_)
- manage.py is outside the Django project(default for Django>=1.4)

.. TODO: where do static files and Templates fit in this structure

.. Note::
    only the third party modules that are to be customised are included in project.
    otherwise they go into prerequisites/dependency list. Also modules included are
    as git submodules so that upstream changes could be merged.
 
django general purpose app structure
------------------------------------

::

    |--pydevprojrct
       |--example_project
       |--tests
       |--docs
       |--app
       |--README.rst
       |--manage.py
       |--.gitignore

..   TODO: python packaging guide 

Version control
===============

git workflow
------------

.. TODO: this section

code hosting
------------

- fork all the third party projects that are going to be used.
- host private code in ``bitbucket``
- all the used and created projects must exist in ``github`` or ``bitbucket``
  acting as master repositories. and project must be on only one of them and not
  in both of them because there is only one master repository. To maintain backup
  of master repositories however, create ``git-mirror`` repository.
- clone projects into local workspace for it to be available off-line
  (clone from our forked repository)

Documentation
=============

- use sphinx

Project Workflow
================

start project
-------------

- create ``README.rst`` and write project vision and what this project does
- create ``docs``

collaborating
-------------

- create apt commit message. commit message must be in proper format(line limit
  80, `short description-blank line-long description` style)
- long description must explain point wise, the rationale behind each change made.
- code review before merging to mainline branch

issue tracking
--------------

- use github/bitbucket issue tracking
- reproduce bug by writing tests while fixing the issue

Project Packaging
=================

.. TODO: this

Project Deployment
==================

.. TODO: how to deploy in production
