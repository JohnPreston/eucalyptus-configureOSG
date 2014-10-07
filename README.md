eucalyptus-configureOSG
=======================

Role to configure Eucalyptus Object Storage Gateway ptoperties

Requirements
------------

Eucalyptus Cloud up and running

Role Variables
--------------

| Parameter | Required | Default | Description
|--- |--- |--- |---
| osg_properties | Yes | [] | List containing the properties name and values for your OSG
| name | Yes | <property name> | Name of the property
| value | Yes | None | Value of the property

List parameters
---------------

| Parameter | Required | Default | Description
|--- |--- |--- |---
| objectstorage.s3provider.s3endpoint | Yes | None | Endpoint of your Object Storage backend
| objectstorage.s3provider.s3accesskey | Yes | None | Object Storage ACCESS Key
| objectstorage.s3provider.s3secretkey | Yes | None | Object Storage SECRET Key

Dependencies
------------

- JohnPreston.eucalyptus-credentials

Example Playbook
----------------

```
- hosts: clc
  roles:
  - JohnPreston.eucalyptus-configureOSG
  vars:
  - osg_provider_name: riakcs
  - osg_properties:
    - {'name': 'objectstorage.s3provider.s3endpoint',
       'value': "http://1.2.3.4:8080" }
    - {'name': 'objectstorage.s3provider.s3accesskey',
       'value': "my_access_key" }
    - {'name': 'objectstorage.s3provider.s3secretkey',
       'value': "my_secret_key" }


```

License
-------

BSD

Author Information
------------------

John Preston [John Mille]

