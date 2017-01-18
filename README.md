STARTUP STUDIO INFRASTRUCTURE
===

This repositoy contains the following tools: 

  - Ruby 2.3.3 with Rails Framework
  - Mysql
  - NGINX

It will take up to **10 minutes to finish the first config**

Usage
===

For new repos, clone including submodules.

```
  git clone --recursive https://github.com/Tinker-Ware/startupstudio-infrastructure.git
```

For already cloned repos, just update the submodules.
```
  git submodule update --init --recursive
```

Start working with the created Vagrant machine:
```
  vagrant up
```
When the process is done, you can view your project in your browser in: `192.168.33.10` in ports
3000 and 4000 by default or depending on your defined variables.

This will create a synced folder with your host machine `./tinker_share_files`.
All the files will be placed there ready to be modified.

HAPPY CODING!

# USE YOUR REPOSITORIES

Modify your github credentials updating `provisioning/host_vars/startupstudio.web`
and define your repos there.

```
rails_repos:
  app1:
    name: https://github.com/RailsApps/learn-rails.git
    port: 3000
    branch: master
```

# USING PRIVATE REPOSITORIES

Make sure to configure everything properly.

Modify your github credentials updating `provisioning/host_vars/startupstudio.web`

```
private_key: yes    # MAKE SURE THIS LINE IS SET TO YES
## GIT
gitconfig:
  user: user     ## ADD YOUR USER
  ssh: yes
  ssh_key_path: "/home/tinkerware/.ssh/ansible_id_rsa"
  option:
    user_email: user@ticonsulting.com  ## ADD YOUR GITHUB EMAIL
    user_name: username   ## ADD YOUR GITHUB USERNAME

```

Include your private key in:
`provisioning/host_files/startupstudio.web/keys/private` in a file as follows:

```
priv_k: |
   << Private key here >>
```


Current Config
===

For development, de database is configured as it follows:

```
root password: rootpass
mysql user: "charlie"
mysql host: "localhost" #Inside the Vagrant. or 192.168.33.10 from the outside.
mysql password: "password"
mysql database name: "ss_database"
```

For Database configurations and yii framework cookie validation key,
go to `provisioning/host_vars/startupstudio.web` if needed.

There you can define your rails repos as well like:
```
rails_repos:
  app1:
    name: https://github.com/RailsApps/rails-signup-download.git
    port: 3000
    branch: master
  app2:
    name: https://github.com/RailsApps/learn-rails.git
    port: 4000
    branch: master
```

If any change is made, contact Tinkerware support. :)

Support
===

Please contact Tinkerware if any request or modification.

email: alfonso@tinkerware.io
Slack: tinkerware-support.slack.com/signin
