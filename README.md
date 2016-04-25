[![Build Status](https://travis-ci.org/lpenz/ansible-testing-netconf.svg?branch=master)](https://travis-ci.org/lpenz/ansible-testing-netconf)

# ansible-testing-netconf

This repository is used for testing the
[netconf](https://tools.ietf.org/html/rfc4741) module in
[ansible-modules-extras](https://github.com/ansible/ansible-modules-extras).

It also serves as an example of how it can be used, as it is a provisioner that
follows ansible's best practices while using the module.

The module itself is tested against
[openyuma](https://github.com/OpenClovis/OpenYuma) and
[netopeer](https://github.com/CESNET/netopeer), both provisioned in the
playbooks with ansible's docker module.

To run the tests, clone this repository and run, inside it:

    git submodule update --init --recursive
    . ./ansible/hacking/env-setup
    cd playbooks
    ansible-playbook --module-path=$PWD/../ansible-modules-extras/network/netconf -i localhost, -c local playbook-openyuma.yml

You should also take a look at the ``.travis.yml`` file, as it is the
"canonical" source code of the test procedure.
