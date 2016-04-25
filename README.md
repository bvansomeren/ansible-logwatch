bvansomeren.logwatch
=========

Installs `Logwatch` and applies changes to the configuration (for example to send emails)

Requirements
------------

None

Role Variables
--------------

You can override the default configuration, see example below:

	logwatch_overrides: []

These contain a map / dict of the configuration changes you want in the override config (location depends on OS).
Example:
	logwatch_overrides:
	- { name: MailTo, config: me@example.com }
	- { name: Print, config: "no" }
	- { name: Output, config: mail }

Dependencies
------------

None

Example Playbook
----------------


    - hosts: all
      become: yes
      become_user: root
      roles:
         - { role: bvansomeren.logwatch, logwatch_overrides: [{ name: MailTo, config: mail@example.com }, { name: Print, config: "no"}, { name: Output, config: mail} ] }

License
-------

MIT

Author Information
------------------

