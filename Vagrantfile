API_VERSION = 2
COREOS_BOX = "https://storage.googleapis.com/%s.release.core-os.net/amd64-usr/%s/coreos_production_vagrant.json"


Vagrant.configure(API_VERSION) do |config|
    config.vm.define "alpha" do |alpha|
        alpha.vm.box_url = COREOS_BOX % ["alpha", "current"]
        alpha.vm.box = "coreos-alpha"
        alpha.vm.hostname = "alpha.coreos.local"
        alpha.vm.provision "ansible" do |ansible|
            ansible.playbook = "test.yml"
            ansible.groups = {
                "coreos" => ["alpha",]
            }
        end
    end

    config.vm.define "beta" do |beta|
        beta.vm.box_url = COREOS_BOX % ["beta", "current"]
        beta.vm.box = "coreos-beta"
        beta.vm.hostname = "beta.coreos.local"
        beta.vm.provision "ansible" do |ansible|
            ansible.playbook = "test.yml"
            ansible.groups = {
                "coreos" => ["beta",]
            }
        end
    end

    config.vm.define "stable" do |stable|
        stable.vm.box_url = COREOS_BOX % ["stable", "current"]
        stable.vm.box = "coreos-stable"
        stable.vm.hostname = "stable.coreos.local"
        stable.vm.provision "ansible" do |ansible|
            ansible.playbook = "test.yml"
            ansible.groups = {
                "coreos" => ["stable",]
            }
        end
    end
end
