gobuild
=========

[![Build Status](https://travis-ci.org/gotansible/gobuild.svg?branch=0.1.1)](https://travis-ci.org/gotansible/gobuild)
[![Ansible Galaxy](http://img.shields.io/badge/galaxy-gotansible.gobuild-blue.svg?style=flat)](https://galaxy.ansible.com/list#/roles/3845)

An ansible role that does builds of golang projects.

Requirements
------------

* Ubuntu / Debian
* CentOS / RedHat

Role Variables
--------------

```yaml
# path on disk
gobuild_project_path: github.com/user/project

# the url to the repository
gobuild_repo_url: https://{{ gobuild_project_path }}

# could be a hash or other marker of a rev
gobuild_repo_version: HEAD

# for private repositories
gobuild_keyfile:  ''

gobuild_go_version: 1.4.2

# use makefile if present
gobuild_makefile_enabled: true

# i.e.: make {target}
gobuild_makefile_target: ''

# any build flags for go
gobuild_build_flags: '-race -v'
# where to do the building
gobuild_dir: /tmp/build

# deploy to the build machine's local filesystem
gobuild_deploy_local: true
gobuild_deploy_dest: /tmp/deploy

# deploy to s3
gobuild_deploy_s3: false
gobuild_s3_key: (AWS access key id)
gobuild_s3_secret: (AWS secret access key)
gobuild_bucket: (S3 bucket name)

```

Dependencies
------------

* none

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
    - role: gotansible.gobuild
	  gobuild_project_path: github.com/youruser/yourproject
```

License
-------

MIT

Author Information
------------------

Created by Franklin Wise in Santa Monica, CA.

