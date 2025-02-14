.. _ec2-then-ec2-devflow:

Compile with Framework API and Deploy on EC2 Inf1
=================================================

.. contents:: Table of Contents
   :local:
   :depth: 3

   
Description
-----------

|image|
 
.. |image| image:: /images/ec2-then-ec2-dev-flow.png
   :width: 500
   :alt: Neuron developer flow on EC2
   :align: middle

You can use a single inf1 instance as a development environment to compile and deploy Neuron models. In this developer flow, you provision an EC2 inf1 instance using a Deep Learming AMI (DLAMI) and execute the two steps of the development flow in the same instance. The DLAMI comes pre-packaged with the Neuron frameworks, compiler, and required runtimes to complete the flow. Development happens through Jupyter Notebooks or using a secure shell (ssh) connection in terminal. Follow the steps bellow to setup your environment. 

.. note::
	**Model compilation can be executed on a non-inf1 instance** for later deployment. 
	Follow the same EC2 Developer Flow Setup using other instance families and leverage `Amazon Simple Storage Service  <https://docs.aws.amazon.com/AmazonS3/latest/userguide/upload-objects.html>`_ (S3) to share the compiled models between different instances.   

.. _ec2-then-ec2-setenv:

Setup Environment
-----------------

1. Launch an Inf1 Instance
^^^^^^^^^^^^^^^^^^^^^^^^^^

    .. include:: /general/setup/install-templates/inf1/launch-inf1-dlami.rst
  

2. Set up a development environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
   
Enable PyTorch-Neuron
~~~~~~~~~~~~~~~~~~~~~

.. include :: /general/setup/install-templates/inf1/note-setup-libnrt-warning.rst

.. include:: /general/setup/install-templates/inf1/dlami-enable-neuron-pytorch.rst

Enable TensorFlow-Neuron
~~~~~~~~~~~~~~~~~~~~~~~~~

.. include :: /general/setup/install-templates/inf1/note-setup-libnrt-warning.rst

.. include:: /general/setup/install-templates/inf1/dlami-enable-neuron-tensorflow.rst

Enable Apache MXNet (Incubating)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include :: /general/setup/install-templates/inf1/note-setup-libnrt-warning.rst

.. include:: /general/setup/install-templates/inf1/dlami-enable-neuron-mxnet.rst

3. Set up Jupyter notebook
^^^^^^^^^^^^^^^^^^^^^^^^^^

To develop from a Jupyter notebook see :ref:`setup-jupyter-notebook-steps-troubleshooting`  

You can also run a Jupyter notebook as a script, first enable the ML framework Conda or Python environment of your choice and see :ref:`running-jupyter-notebook-as-script` for instructions. 
