VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define 'app' do |app|
    app.vm.box = 'ubuntu/trusty64'
    app.vm.network :private_network, ip: '10.0.0.90'
  end

  config.vm.define 'db' do |db|
    db.vm.box = 'ubuntu/trusty64'
    db.vm.network :private_network, ip: '10.0.0.91'
  end

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true

    ###################
    ## 001_playbooks ##
    ###################

    ansible.playbook = "001_playbooks/playbook.yml"


    ###################
    ## 002_inventory ##
    ###################

    # ansible.playbook = "002_inventory/playbook.yml"
    # ansible.inventory_path = "002_inventory/development"


    ###############
    ## 003_roles ##
    ###############

    # ansible.playbook = "003_roles/playbook.yml"
    # ansible.inventory_path = "003_roles/development"


    ###################
    ## 004_variables ##
    ###################

    # ansible.playbook = "004_variables/playbook.yml"
    # ansible.inventory_path = "004_variables/development"


    ####################
    ## 005_targetting ##
    ####################

    ## 1. Execute entire playbook
    ##    ansible-playbook 005_targetting/playbook.yml -i 005_targetting/development
    # ansible.playbook = "005_targetting/playbook.yml"
    # ansible.inventory_path = "005_targetting/development"

    ## 2. Execute `common` role on all servers
    ##    ansible-playbook 005_targetting/playbook.yml -i 005_targetting/development -t common
    # ansible.playbook = "005_targetting/playbook.yml"
    # ansible.inventory_path = "005_targetting/development"
    # ansible.tags = ['common']

    ## 3. Execute `common` role only on app servers
    ##    ansible-playbook 005_targetting/app-servers.yml -i 005_targetting/development -t common
    # ansible.playbook = "005_targetting/app-servers.yml"
    # ansible.inventory_path = "005_targetting/development"
    # ansible.tags = ['common']

    ## 4. Execute all roles except `redis`
    ##    ansible-playbook 005_targetting/app-servers.yml -i 005_targetting/development --skip-tags redis
    # ansible.playbook = "005_targetting/playbook.yml"
    # ansible.inventory_path = "005_targetting/development"
    # ansible.skip_tags = ['redis']
  end
end
