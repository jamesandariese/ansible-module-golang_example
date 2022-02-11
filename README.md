# Ansible Collection - `strudelline.golang_example`

This collection is an example of how to create a golang module
for ansible.  Use it as a skeleton or to generate primes if you
need them in ansible for some reason :D

Enjoy!

## Customizing

To create your own prime seive module, you may update this module entirely with search and replace.  It is name independent as is to make it easy to modify.

### Search and replace keywords
The keywords to change are as follows:

* `strudelline` - your namespace
* `golang_example` - your collectionname
* `generate_prime` - your module's name
* `James Andariese` - your name
* `james@strudelline.net` - your email address


### Steps
Making this into your own module requires some steps:

1) fork the `golang_example` repo (a github fork or cloning and making a new one are both fine)
2) create your module (e.g. named `stuff_things`)
  1) create a folder with a go module (`go help mod init` at `golang_modules/stuff_things`
  2) copy `plugins/action/generate_prime.py` to `plugins/action/stuff_things.py`
  3) copy `plugins/modules/generate_prime.py` to `plugins/modules/stuff_things.py`
  4) edit `plugins/modules/generate_prime.py` to include documentation (this file only has docs)
3) modify galaxy.yml
  1) modify relevant fields, especially the namespace and author
  2) in `build_ignore` change `generate_prime_*` to `stuff_things_*` (note the underscore -- this is to keep the binary module from accidentally going to ansible-galaxy -- it will be too large!)
4) modify `test/test-playbook.yml` with the new module and collection names
5) modify this README.md
