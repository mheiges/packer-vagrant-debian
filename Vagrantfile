
deb_ver=ENV['debian']
if ! ENV['type'].nil?
  suffix="-#{ENV['type']}"
end

Vagrant.configure("2") do |config|
  config.vm.hostname = "debian#{deb_ver}#{suffix}.vm"
  config.vm.box = "mheiges/debian-#{deb_ver}-64#{suffix}"

  config.vm.network :private_network, type: :dhcp
  config.vm.synced_folder '.', '/vagrant', type: 'nfs'

  config.vm.provider :virtualbox do |v|
    v.gui = false
    v.memory = 1024
    v.cpus = 1
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  if Vagrant.has_plugin?('landrush')
    config.landrush.enabled = true
    config.landrush.tld = "vm"
    config.landrush.host "debian#{deb_ver}#{suffix}.vm"
  end

end
