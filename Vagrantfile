Vagrant.configure(2) do |config|
  config.vm.box = 'ubuntu/xenial64'

  machines = %w(grafana app)
  machines.each_with_index do |machine, index|
    config.vm.define machine do |conf|
      conf.vm.network :private_network, ip: "192.168.10.#{10 + index}"

      if index == machines.length - 1 then
        conf.vm.provision :ansible,
          limit: 'all',
          playbook: '/etc/ansible/roles/bootstrap/bootstrap.yml'
        conf.vm.provision :ansible,
          limit: 'all',
          playbook: 'playbooks/grafana-stack.yml',
          groups: { grafana: %w(grafana),
                    app: %w(app),
                    'prometheus:children': %w(grafana app) },
          raw_arguments: %w(--diff -vvv)
      end
    end
  end
end
