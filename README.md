Ansible role: rpi-boot-config
=============================

Minimal role to manage config entries in a Raspberry PI [boot config](http://www.raspberrypi.org/documentation/configuration/config-txt.md). After changing the boot config, it will restart the raspberry pi and wait for it to come back. This requires that the *ansible_host* is set correctly in the inventory:

	[all]
	raspberry ansible_host=192.168.1.101


Requirements
------------

Nothing specific so far.

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

	boot_config: {}

This is the only variable for this role right now. If used, it has to be a dictionary with key value pairs, each of which will be set in the boot config. Example:

	boot_config:
		gpu_mem: 196

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: raspberrypis
      roles:
	      - { role: rpi_boot_config, boot_config: {'gpu_mem': '196'} }

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2016 by Paul Kremer.

