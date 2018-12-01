# Apigee OPDK Mirror Archive Creator

This role will create an Apigee Mirror to be used to install Apigee in an offline environments.

Requirements
------------

The Apigee Bootstrap must be installed so that the Apigee Service component is available prior to 
running this role. 

Role Variables
--------------

These are the variables that can be updated for this role:

| Name | Description |
| --- | --- |
| copy_archive | Copy the Apigee Mirror archive from the control machine or use an existing archive on a target server. Default: `copy_archive: yes` |
| apigee_home | Apigee installation home. Default: /opt/apigee |
| no_proxy | no proxy environment variable. Default: '' |
| http_proxy | http proxy environment variable. Default: '' |
| https_proxy | https proxy environment variable. Default: '' |
| apigeereleasever | Apigee release version. Default: opdk_version |
| archive_extra_packages | List of extra packages to include in the archive. Default list: yum-utils, yum-plugin-priorities, libdb4-4.8* |

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: mirror
      vars: 
        copy_archive: yes
        apigee_home: /opt/apigee
        opdk_version: 4.18.05
        apigeereleasever: 4.18.05
        archive_extra_packages: 
        - yum-utils
        - yum-plugin-priorities
        - libdb4-4.8*
        
      roles:
      - { role: apigee-opdk-setup-bootstrap-create-archive, tags: ['create'] }

License
-------

Apache 2.0

Author Information
------------------

Carlos Frias

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
<!-- BEGIN Google Required Disclaimer -->

# Not Google Product Clause

This is not an officially supported Google product.
<!-- END Google Required Disclaimer -->
<!-- BEGIN Google How To Contribute -->
# How to Contribute

We'd love to accept your patches and contributions to this project. Please review our [guidelines](CONTRIBUTING.md).
<!-- END Google How To Contribute -->
