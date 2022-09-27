
nodes = [
    { :hostname => 'pc1', :ip => '192.168.1.3', :memory => 1024, :cpu => 1, :boxname => "generic/ubuntu2010"},
    { :hostname => 'pc2', :ip => '192.168.1.4', :memory => 1024, :cpu => 1, :boxname => "generic/ubuntu2010"},
]

Vagrant.configure("2") do |config|
    nodes.each do |node|
        config.vm.box_check_update = false
        config.vm.define node[:hostname] do |nodeconfig|
            nodeconfig.vm.box = node[:boxname]
            nodeconfig.vm.hostname = node[:hostname]
            nodeconfig.vm.network :private_network, ip: node[:ip]

            nodeconfig.vm.provider :hyperv do |vb|
                vb.memory = node[:memory]
                vb.cpus = node[:cpu]
            end
        end
    end
end

