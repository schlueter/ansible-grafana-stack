Vagrant.configure(2) do |config|
  config.vm.box = 'ubuntu/xenial64'
  config.vm.network :private_network, ip: '192.168.29.7'
  config.vm.provision 'shell',
    inline: 'apt-get install -y python-minimal',
    privileged: true
  config.vm.provision :ansible,
    playbook: 'playbooks/cig.yml',
    groups: { cig: %w(default) },
    raw_arguments: %w(--diff -vvv)
end
