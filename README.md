# Cowseii
### With all due respect to 'cowsay'

I was looking into Ansible and discovered that it will use the [cowsay](https://github.com/schacon/cowsay) program by default if that program is installed. However, cowsay is bound into a fixed graphic and doesn't always look quite right when many lines of an Ansible playbook are scrolling past.

What if it were tweaked a little to allow free-form text, while maintaining all the same functionality that people knew and loved?

```
             _____
 __          \   /
|  |_________| * |-------------------------------------------\
|  |         | * | TASK [Output text in a more display-friendly way]
|  |_________| * |                                             \
|__|         | * |----------------------------------------------\
             /___\
```

I am not a Perl programmer, and this tweak is not intended as a new version of "cowsay". However, it does maintain compatibility completely as far as I can tell. Other than the binary name changing, you shouldn't notice any difference until using a `.cow` file which contains the `TEXT` tag.

## USAGE

Install as shown in "INSTALL" file.
For use with [https://www.ansible.com/](Ansible) playbooks, alter your `ANSIBLE_COW_PATH` variable [1] to point to the `cowseii` binary.
For a more Ansible-friendly display, set `ANSIBLE_COW_SELECTION` to `sword.cow`.

**NOTE:** Cowseii will try not to overwrite any existing installs of `cowsay`, symlink itself to `cowthink`, or overwrite any existing `.cow` files in the default locations. Any `.cow` files that were not already present, however, will be installed.


For the terms and conditions of use, consult the LICENSE file in
this directory.

[1]: https://docs.ansible.com/ansible/latest/reference_appendices/config.html#ansible-cow-path
