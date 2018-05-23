EC2 Instance Handler
====================

Introduction
------------

This repo is to handle the EC2 instance using python script. It can Start/Stop the instance.


Prerequisite
-------------

* EC2 instances already created for a region.
* To connect locally, give access key and access secret key by changing inside the file ~/.aws/credentials
* The parameter -e (--env) to be passed to fetch the env access key and secret access from the file.
* To change it to different file, make the changes inside constant.py
* env must be configured in config.ec2_instances.py
* To exclude any critical instance, mention it as excluded instance inside ec2_instance.py under the region.


Fixes
-----
* User can create multiple Env for one or different regions.
* User can exclude one or more instances for a region by changing in ec_instance.py
* Will not let stop/start instance with similar name. It will work only instances which are exactly matching with given one.
* Raises exception on No instance being passed to boto3.

Command:
----------
    python start_stop_ec2.py -a <action> -e <env>

    python start_stop_ec2.py -a start -e test_server

Here, action can be start or stop

env can be your environment/account which you have configured inside ~/.aws/credentials and config.ec2_instances.py

Contributions:
--------------
Modifications are done by `Amit Yadav <https://github.com/Coder-AMiT>`_
