# Check role last chef-client execution
knife status 'role:web' --run-list

# Upload new version of cookbook to chef-server
knife cookbook upload learn_chef_httpd

# Manually execute chef-client on chef node
knife ssh localhost --ssh-port 2200 'sudo chef-client' --manual-list --ssh-user vagrant --identity-file /Users/ret/Projects/chef-tutorial/.vagrant/machines/node1-centos/virtualbox/private_key

# View roles of a chef node
knife node show node1-centos --run-list

# List chef nodes attached to chef-server instance
knife node list

# View details of a chef node
knife node show node1-centos

# List available roles
knife role list

# Upload role to chef-server
knife role from file roles/web.json

# Show role details 
knife role show web

# Delete role
knife role delete web --yes

# Delete cookbook from chef server
knife cookbook delete learn_chef_httpd --all --yes

# Delte node from chef server
knife node delete node1-centos --yes

# Delte client from chef server
knife client delete node1-centos --yes
