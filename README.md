vbox_additions
==============

Role that helps to install VirtualBox Additions.


Example
-------

```
---

# Example of how to install a specific version
- hosts: myhost
  vars:
    vbox_additions_version: 5.0.18
  roles:
    - vbox_additions

# Example of how to use locally downloaded ISO instead of downloading it from the web
- hosts: myhost
  vars:
    vbox_additions_version: 5.0.18
    vbox_additions_local_iso: ~/Downloads/VBoxGuestAdditions_{{ vbox_additions_version }}.iso
  roles:
    - vbox_additions

# Example of how to ignore build errors
- hosts: myhost
  vars:
    vbox_additions_version: 5.0.18
    vbox_additions_local_iso: ~/Downloads/VBoxGuestAdditions_{{ vbox_additions_version }}.iso
    vbox_additions_build_ignore_errors: yes
  roles:
    - vbox_additions
```


Role variables
--------------

List of variables used by the role:

```
# Additions version
vbox_additions_version: 5.0.18

# Path to locally downloaded ISO image
# (if specified, no ISO will be downloded from the web)
vbox_additions_local_iso: ""

# Where to downlod the ISO
vbox_additions_iso_url: http://download.virtualbox.org/virtualbox/{{ vbox_additions_version }}/VBoxGuestAdditions_{{ vbox_additions_version }}.iso

# Where to store the ISO
vbox_additions_iso_path: /tmp/VBoxGuestAdditions_{{ vbox_additions_version }}.iso

# Whether to remove the ISO after successfull installation
vbox_additions_iso_remove: yes

# Build dependencies
vbox_additions_build_deps:
  - gcc
  - kernel-devel
  - bzip2
  - perl

# Whether to force the build even if modules exist
vbox_additions_build_force: no

# Whether to force the build even if modules exist
vbox_additions_build_ignore_errors: no

# Whether to uninstall the build dependencies once finished
vbox_additions_build_deps_uninstall: yes
```


Dependencies
------------

- [vagrant_user](https://github.com/jtyr/ansible-vagrant_user) (optional)


License
-------

MIT


Author
------

Jiri Tyr
