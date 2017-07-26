# Grafana Stack
This is an Ansible project which can set up various monitoring stacks presenting data from a number of different data sources. Currently, only Prometheus is configured.

# Setup
`git clone git@github.com:schlueter/ansible-grafana-stack.git --recurse`

# Vagrant
`vagrant up` will bring up a Grafana + Prometheus instance exposing Grafana on [192.168.29.7:3000](http://192.168.29.7:300) and Prometheus on [192.168.29.7:9090](http://192.168.29.7:9090).

