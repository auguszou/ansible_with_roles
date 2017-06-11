Ruby-Build
==========

Install ruby system-wide. No RVM/Rbenv, just one ruby and it's Very easy to manage.

It uses ruby-build https://github.com/sstephenson/ruby-build, available `ruby_version` are the one documented/updated in ruby-build.

Requirements
------------

 - None

Role Variables
---------------

```yaml
---
apt_update: yes  # allow to execute `apt-get update'
ruby_gems:       # list of gems to install
  - name: bundler
ruby_version: 2.2.0  # ruby version
ruby_packages:       # required packages to compile ruby
  - autoconf
  - automake
  - bison
  - libssl-dev
  - libyaml-dev
  - libreadline6
  - libreadline6-dev
  - zlib1g
  - zlib1g-dev
  - libxml2-dev
  - libffi-dev
  - wget
  - libpq-dev
  - build-essential

```

Dependencies
------------

 - None

Example Playbook
----------------

```yaml
---
- hosts: rails-app
  roles:
  - role: ruby-build
    ruby_version: rbx-2.1.0
```

License
-------

MIT
