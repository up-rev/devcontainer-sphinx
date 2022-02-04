Uprev Sphinx Dev Container
==========================

This project contains the dockerfile for the `uprev/sphinx <https://hub.docker.com/repository/docker/uprev/sphinx>`_ docker image. 

The dockerfile has 2 stages. The dev stage has all of the required tools for building a sphinx project, and the jenkins stage adds on the dependencies to run as a jenkins node. 


Using the image 
---------------

|

VS Code 
~~~~~~~

The easiest way to use this is with the VS Code remote container extension. 

#. Copy to the `.devcontainer` folder to your Sphinx project 
#. Open the project directory in VS Code 
#. Click the green `Remote Window` button in the bottom left corner 
#. click 'Reopen in Container'


This will pull the latest uprev/sphinx image from docker hub, run it, and mount the project to it. The devcontainer settings will automatically install the VS Code extensions commonly used in doc project: 

*   rST support
*   Drawio
*   Plantuml (Syntax highlighting, preview, autocomplete) 

|

Jenkins 
~~~~~~~

The image has all of the necesary requirements to run as a jenkins node. Run the container, and then set up jenkins to connect via SSH

.. code:: bash 

    docker run uprev/sphinx -p 22:22 --name sphinx uprev/sphinx

.. tip:: to map to a different port change the port mapping argument to `-p <desired port>:22`

|

command line 
~~~~~~~~~~~~

.. code:: bash 

    docker run -it uprev/sphinx bash