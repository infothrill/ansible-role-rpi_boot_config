Ansible role: rpi-boot-config
=============================

Minimal role to manage config entries in a Raspberry PI [boot config](http://www.raspberrypi.org/documentation/configuration/config-txt.md). After changing the boot config, it will restart the raspberry pi and wait for it to come back. This requires either the `inventory_hostname` is resolvable or that the `ansible_host` is set correctly in the inventory:

	[all]
	raspberry ansible_host=192.168.1.101


Requirements
------------

Nothing specific so far.

Role Variables
--------------

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


Dependencies
------------

None.

Example Playbook
----------------

    - hosts: raspberrypis
      roles:
	      - { role: rpi_boot_config, boot_config_lines: ['gpu_mem=196'] }

Changelog
---------

### 1.1
* added new, optional variable `boot_config_lines`

### 1.0
* initial release


License
-------

MIT / BSD

Author Information
------------------

This role was created in 2016 by Paul Kremer.

