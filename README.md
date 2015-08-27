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
external_url 'http://localhost:8880'
unicorn['port'] = 8181
postgresql['enable'] = true
postgresql['port'] = 6543
postgresql['data_dir'] = "/var/opt/gitlab/postgresql/data"
```
And then
```sh
# gitlab-ctl reconfigure
# gitlab-ctl start
for trace error
# gitlab-ctl tail
```

Browse to the hostname and login

Username: root 
Password: 5iveL!fe

### Enable apache mod proxy to gitlab
```sh
# vi /etc/httpd/conf/httpd.conf
LoadModule proxy_module modules/mod_proxy.so
LoadModule proxy_http_module modules/mod_proxy_http.so
```

### Edit url for email confirm if using Varnish
```sh
# vi /var/opt/gitlab/gitlab-rails/etc/gitlab.yml
  gitlab:
    ## Web server settings (note: host is the FQDN, do not include http://)
    host: git.vas.web.id
    port: 80
    https: false

```

### Setting Using Resource Memory Kernel
```sh
# sysctl -w kernel.shmmax=17179869184
# sysctl -w kernel.shmall=4194304

```


### GitLab Detail:

Main Configuration File: /var/opt/gitlab/gitlab-rails/etc/gitlab.yml
GitLab Document Root: /opt/gitlab
Default Repository Location: /var/opt/gitlab/git-data/repositories
Default Nginx Configuration File: /opt/gitlab/embedded/conf/nginx.conf
GitLab Nginx Configuration file Location: /var/opt/gitlab/nginx/conf
Postgresql data Directory: /var/opt/gitlab/postgresql/data


http://stackoverflow.com/questions/29949294/how-to-configure-gitlab-to-use-existing-postgres-server

http://stackoverflow.com/questions/10954516/apache2-proxypass-for-rails-app-gitlab

http://serverfault.com/questions/585528/set-gitlab-external-web-port-number

http://serverfault.com/questions/512527/gitlab-with-apache-proxy


