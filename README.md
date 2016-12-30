TI CONSULTING INFRASTRUCTURE
===

This repositoy contains the following tools:

  - Ruby 2.3.3 with Rails Framework
  - Mysql
  - NGINX

Usage
===

For new repos, clone including submodules.

```
  git clone --recursive https://github.com/Tinker-Ware/ticonsulting-infrastructure.git
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

Current DB Config
===

For development, de database is configured as it follows:

```
root password: rootpass
mysql user: "ticonsulting"
mysql host: "localhost" #Inside the Vagrant. or 192.168.33.10 from the outside.
mysql password: "password"
mysql database name: "ti_database"
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
