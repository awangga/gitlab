# gitlab
Gitlab Installation for Centos 6

```sh
# yum install curl openssh-server postfix cronie
# service postfix start
# chkconfig postfix on
# lokkit -s http -s ssh
```

```sh
# curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | bash
# yum install gitlab-ce
```
edit file /etc/gitlab/gitlab.rb
```sh
# gitlab-ctl reconfigure
```

Browse to the hostname and login

Username: root 
Password: 5iveL!fe


http://stackoverflow.com/questions/29949294/how-to-configure-gitlab-to-use-existing-postgres-server

http://stackoverflow.com/questions/10954516/apache2-proxypass-for-rails-app-gitlab

http://serverfault.com/questions/585528/set-gitlab-external-web-port-number

http://serverfault.com/questions/512527/gitlab-with-apache-proxy


