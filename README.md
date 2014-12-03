chef-notes
==========

### Chef Server Installation/Configuration
```sh
# Source: http://docs.getchef.com/install_server.html
# Download the Chef Server V12 from https://downloads.chef.io/
sudo dpkg -i chef-server-core_12.0.0-1_amd64.deb

# Run the following to start all of the services:
sudo chef-server-ctl reconfigure

# Run the following command to create an administrator:
# chef-server-ctl user-create user_name first_name last_name email password --filename FILE_NAME
sudo chef-server-ctl user-create stevedanno Steve Danno steved@getchef.com abc123 --filename /path/to/file.key

# Run the following command to create an organization:
# chef-server-ctl org-create short_name full_organization_name --association_user user_name --filename FILE_NAME
sudo chef-server-ctl org-create chef Chef Software, Inc. --association_user stevedanno --filename /path/to/file.key
```

#### ChefDK Commands
```sh
# Run a single recipe from the command line
sudo chef-apply <filename>

# Generate a cookbook
chef generate cookbook learn_chef_apache2

# Generate a template
chef generate template learn_chef_apache2 index.html

# Run a cookbook
sudo chef-client --local-mode --runlist 'recipe[learn_chef_apache2]'
```
