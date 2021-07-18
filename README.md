# Ansible role: rpi_boot_config

![Build status](https://github.com/infothrill/ansible-role-rpi_boot_config/actions/workflows/tests.yml/badge.svg)
[![Ansible Role](https://img.shields.io/ansible/role/50818.svg)](https://galaxy.ansible.com/infothrill/rpi_boot_config/)


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

**rpi\_boot\_config\_file**, optional

Path of the Raspberry Pi boot configuration file to manage, default: `/boot/config.txt`. Example:

```
rpi_boot_config_file: /boot/config.txt
```

## Dependencies

None.

## Example Playbook

    - hosts: raspberrypis
      roles:
	      - { role: rpi_boot_config, boot_config_lines: ['gpu_mem=196'] }

## Changelog

### 4.2.0

* moved CI to Github Actions
* drop support for ansible 2.9, python3.7

### 4.1.0

* upgraded CI tests to use python3.7+
* upgraded molecule to version 3.x
* drop support for ansible 2.8
* add configurable path to boot config file

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

