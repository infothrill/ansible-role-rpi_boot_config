# Ansible role: rpi_boot_config

[![Build Status](https://img.shields.io/travis/infothrill/ansible-role-rpi_boot_config/master.svg?label=travis_master)](https://travis-ci.org/infothrill/ansible-role-rpi_boot_config)
[![Build Status](https://img.shields.io/travis/infothrill/ansible-role-rpi_boot_config/develop.svg?label=travis_develop)](https://travis-ci.org/infothrill/ansible-role-rpi_boot_config)
[![Updates](https://pyup.io/repos/github/infothrill/ansible-role-rpi_boot_config/shield.svg)](https://pyup.io/repos/github/infothrill/ansible-role-rpi_boot_config/)
[![Ansible Role](https://img.shields.io/ansible/role/12477.svg)](https://galaxy.ansible.com/infothrill/rpi_boot_config/)


Minimal role to manage config entries in a Raspberry PI [boot config](http://www.raspberrypi.org/documentation/configuration/config-txt.md). After changing the boot config, it will restart the raspberry pi and wait for it to come back.


## Requirements

Nothing specific so far.

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

**boot\_config\_lines**, optional

List of verbatim config lines to be put into `/boot/config.txt` (no assertions about uniqueness are made). Example:

```
boot_config_lines:
	- "gpu_mem=196"
	- "dtoverlay=pi3-disable-wifi"
	- "dtoverlay=pi3-disable-bt"
```


**boot\_config**, optional

Dictionary where every key translates to a unique setting in `/boot/config.txt`. Example:

```
boot_config:
	gpu_mem: '196'
```


## Dependencies

None.

## Example Playbook

    - hosts: raspberrypis
      roles:
	      - { role: rpi_boot_config, boot_config_lines: ['gpu_mem=196'] }

## Changelog

### 4.0.0

* renamed role to `rpi_boot_config`
* drop support for ansible 2.7

### 3.0.0

* use ansible `reboot` module
* drop support for ansible 2.5, 2.6

### 2.0.0

* drop support for python2
* add support for ansible 2.9
* add support for debian buster
* upgraded ansible-lint

### 1.1.1

* introduce semver release numbering
* expand tested OS to raspbian jessie, buster
* switch to molecule testing framework

### 1.1
* added new, optional variable `boot_config_lines`

### 1.0
* initial release


## License

MIT / BSD

## Author Information

This role was created in 2016 by Paul Kremer.

