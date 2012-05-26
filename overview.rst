########
Workflow
########


This is the documentation of general guide lines, standards, recommendations and
strategies used for the development of web projects. This also covers the code
management, work environments setup, development/release cycle, deployment,
packaging, documentation, django specific project structure, git version
control , git workflows and code hosting.


Development environment
=======================
**Eclipse pydev as IDE**

Eclipse plugins used:

- Rest plugin
- Egit

Python prerequisites:

- sphinx
- virtualenv
- pip


Project Guide-Lines
-------------------

- Create virtual environment for each project

Pydev project structure
-----------------------

::
    
    |--PydevProject
       |--docs
       |--djangoproject
       |--thirdpartymodulecustomized1    #included as git submodules 
       |--thirdpartyappcustomized1       #included as git submodules
       |--tests
       |--README.rst
       |--.gitignore

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
- host private code in bitbucket
- all the used and created projects must exist in github or bitbucket
  acting as master repo. and project must be on only one of them not
  both of them because there is only one master repo
- clone projects into local workspace for it to be available offline
  (clone from our forked repo)

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

- create apt commit message
- code review before merging to mainline branch

issue tracking
--------------

- use github/bitbucket issue tracking
- reproduce bug by writing tests while fixing the issue

