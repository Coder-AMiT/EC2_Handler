EC2 Instance Handler
====================

Introduction
------------

This repo is to handle the EC2 instance using python script. It can Start/Stop the instance.


Prerequisite
-------------

* EC2 instances already created for a region.
* Create the profile inside ~/.aws/config , set the region for the profile
* Give access and secret access key for the same profile inside the file ~/.aws/credentials
* env (profile) must be configured in ec2_instances.py , ~/.aws/config and ~/.aws/credentials
* To exclude any critical instance, mention it as excluded instance inside ec2_instance.py under the region.


Formats
--------
~/.aws/credentials

    [default]

    aws_access_key_id=<aws_access_key>

    aws_secret_access_key=<aws_secret_access_key>


    [user2]

    aws_access_key_id=<aws_access_key>

    aws_secret_access_key=<aws_secret_access_key>


~/.aws/config

    [default]

    region=us-west-2

    [profile user2]

    region=us-east-1

`AWS Profile creation <https://docs.aws.amazon.com/cli/latest/userguide/cli-multiple-profiles.html>`_


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
