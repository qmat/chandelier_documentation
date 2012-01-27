QMAT Chandelier - Documentation
======================

This repository holds the technical documentation and design files for the MATLab chandelier in the G2 space at Queen Mary, University of London. If there's something you'd like to know that's not mentioned here, contact Vincent Akkermans or Matt Jarvis.

Physical  design
==========

3D model
--------

This_ directory contains a Rhino [#]_ model and several screenshots of the initial design of the chandelier. It shows two rings of the 17 inch Hannstar HSD170ME13 panels, although in the final product the outer ring is made up out of 19 inch screens.

.. _This: files/rhino_models/chandelier/

.. image:: /qmat/chandelier_documentation/raw/master/files/rhino_models/chandelier/chandelier_screenshot2.png

The specification for the ring can be found here_.

.. _here: /qmat/chandelier_documentation/raw/master/files/dimensions_steel_ring.png

Rigging
------

The screens hang from the ring with nylon straps. The ring is held up by four 5mm steel wires and the two are connected by a small nylon sling and Reutlingers. The steel wires finally connect to the I-beams with shackles and long slings. This repository also contains the safety_ documentation.

.. _safety: files/safety_documentation/

The installation was done by a professional rigger. Ask Matt or Vincent about the contact details if necessary.

Software and deployment
================

Quatz and Infohub
---------------

The chandelier software consists of two main applications: the Quatz application and the Infohub web application. Quatz_ is a Cocoa application that drives the screens by loading Web or Quartz Composer views. What is displayed by the Quatz application is determined by the Infohub application. Infohub_ is a Django python web site which allows users to upload Processing sketches and Quartz Composer files. These can then be displayed on the chandelier by changing the display mode on the infohub website.

.. _Quatz: http://www.github.com/qmat/chandelier_quatz/
.. _Infohub: http://www.github.com/qmat/chandelier_infohub/

Both applications are deployed on the Mac Mini. Access to the website from outside the university is achieved by using SSH tunnels. Currently the website is live at http://www.twobbler.net:9000.

The Infohub application does not only serve to administer the chandelier, it also aggregates updates from the web services the MAT group uses. Currently these are Google Docs, Github, GMail, qmat.net, qmat.net/wiki, twitter, and Vimeo. Infohub's python requirements can be installed by using pip on the requirements.txt file in that is in the root directory of the Infohub repository.

The Quatz and Infohub applications communicate using the ZeroMQ [#] library. The Quatz application can be manually started or stopped from the web site. The Infohub web application is daemonized by Apple's launchd and runs behind Nginx in a reverse proxy configuration.

.. image:: /qmat/chandelier_documentation/raw/master/files/software/deployment.png



Hardware
======

diagram

Screen
- Hannstar HSD170ME13

ems boxes

mac mini<br>

TO DO / Bugs
=========


Future features
==========

real processing view

mode sequencer

interactivity

tie in room sensors

helmet cam


.. [#] http://www.rhino3d.com/
.. [3] http://www.zeromq.org/
