# CGarya
new a commit
test msg

[root@linuxhelp ~]# wget http://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm
--2017-11-06 10:35:05--  http://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm
Resolving packages.erlang-solutions.com (packages.erlang-solutions.com)... 31.172.186.53
Connecting to packages.erlang-solutions.com (packages.erlang-solutions.com)|31.172.186.53|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1932 (1.9K) [application/x-redhat-package-manager]
Saving to: ‘erlang-solutions-1.0-1.noarch.rpm.1’

100%[======================================>] 1,932       --.-K/s   in 0s      

2017-11-06 10:35:43 (86.9 MB/s) - ‘erlang-solutions-1.0-1.noarch.rpm.1’ saved [1932/1932]


[root@linuxhelp ~]# rpm -Uvh erlang-solutions-1.0-1.noarch.rpm
Preparing...                          ################################# [100%]
Updating / installing...
   1:erlang-solutions-1.0-1           ################################# [100%]
--2017-11-06 10:18:02--  http://packages.erlang-solutions.com/rpm/centos/erlang_solutions.repo
Resolving packages.erlang-solutions.com (packages.erlang-solutions.com)... 31.172.186.53
Connecting to packages.erlang-solutions.com (packages.erlang-solutions.com)|31.172.186.53|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 245
Saving to: ‘erlang_solutions.repo’

100%[======================================>] 245         --.-K/s   in 0s      

2017-11-06 10:18:03 (21.0 MB/s) - ‘erlang_solutions.repo’ saved [245/245]
The RPM for Erlang has been installed in the target system. Now install Erlang application by running the yum install command. 

[root@linuxhelp ~]# yum install erlang
Loaded plugins: fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: centos.mirror.snu.edu.in
 * epel: mirror.ehost.vn
 * extras: centos.mirror.snu.edu.in
 * updates: centos.mirror.snu.edu.in
Resolving Dependencies
--> Running transaction check
---> Package erlang.x86_64 0:20.1-1.el7.centos will be installed
--> Processing Dependency: erlang-inets(x86-64) = 20.1-1.el7.centos for package: erlang-20.1-1.el7.centos.x86_64
.
.
.
.
erlang-wx.x86_64 0:20.1-1.el7.centos                                          
  erlang-xmerl.x86_64 0:20.1-1.el7.centos                                       
  mesa-libGLU.x86_64 0:9.0.0-4.el7                                              
  unixODBC.x86_64 0:2.3.1-11.el7                                                
  wxBase.x86_64 0:2.8.12-20.el7                                                 
  wxGTK.x86_64 0:2.8.12-20.el7                                                  
  wxGTK-gl.x86_64 0:2.8.12-20.el7                                               

Complete!
Download the RabbitMQ RPM using wget command followed by the download link. 

[root@linuxhelp ~]# wget https://www.rabbitmq.com/releases/rabbitmq-server/v3.6.1/rabbitmq-server-3.6.1-1.noarch.rpm
--2017-11-06 10:58:49--  https://www.rabbitmq.com/releases/rabbitmq-server/v3.6.1/rabbitmq-server-3.6.1-1.noarch.rpm
Resolving www.rabbitmq.com (www.rabbitmq.com)... 104.20.63.197, 104.20.62.197, 2400:cb00:2048:1::6814:3ec5, ...
Connecting to www.rabbitmq.com (www.rabbitmq.com)|104.20.63.197|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5088884 (4.9M) [application/x-redhat-package-manager]
Saving to: ‘rabbitmq-server-3.6.1-1.noarch.rpm’

100%[======================================>] 5,088,884   1.10MB/s   in 4.5s   

2017-11-06 10:58:54 (1.09 MB/s) - ‘rabbitmq-server-3.6.1-1.noarch.rpm’ saved [5088884/5088884]
Execute the RPM for RabbitMQ by running the following command.  

[root@linuxhelp ~]# rpm --import https://www.rabbitmq.com/rabbitmq-signing-key-public.asc
Install the RabbitMQ application by executing the yum install command.  

[root@linuxhelp ~]# yum install rabbitmq-server-3.6.1-1.noarch.rpm
Loaded plugins: fastestmirror, langpacks
Examining rabbitmq-server-3.6.1-1.noarch.rpm: rabbitmq-server-3.6.1-1.noarch
Marking rabbitmq-server-3.6.1-1.noarch.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package rabbitmq-server.noarch 0:3.6.1-1 will be installed
--> Finished Dependency Resolution
.
.
.
.
Transaction test succeeded
Running transaction
  Installing : rabbitmq-server-3.6.1-1.noarch                               1/1 
  Verifying  : rabbitmq-server-3.6.1-1.noarch                               1/1 

Installed:
  rabbitmq-server.noarch 0:3.6.1-1                                              

Complete!
Start and enable your RabbitMQ by running the following command. 

[root@linuxhelp ~]# systemctl enable rabbitmq-server
rabbitmq-server.service is not a native service, redirecting to /sbin/chkconfig.
Executing /sbin/chkconfig rabbitmq-server on
The unit files have no [Install] section. They are not meant to be enabled
using systemctl.
Possible reasons for having this kind of units are:
1) A unit may be statically enabled by being symlinked from another unit's
   .wants/ or .requires/ directory.
2) A unit's purpose may be to act as a helper for some other unit which has
   a requirement dependency on it.
3) A unit may be started when needed via activation (socket, path, timer,
   D-Bus, udev, scripted systemctl call, ...).
Start the RabbitMQ service. 

[root@linuxhelp ~]# systemctl start rabbitmq-server
Next install Redis application by executing the yum install command. 

[root@linuxhelp ~]# yum install redis
Loaded plugins: fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: centos.mirror.snu.edu.in
 * epel: epel.scopesky.iq
 * extras: centos.mirror.snu.edu.in
 * updates: centos.mirror.snu.edu.in
Resolving Dependencies
--> Running transaction check
---> Package redis.x86_64 0:3.2.10-2.el7 will be installed
--> Processing Dependency: libjemalloc.so.1()(64bit) for package: redis-3.2.10-2.el7.x86_64
.
.
.
Running transaction
  Installing : jemalloc-3.6.0-1.el7.x86_64                                  1/2 
  Installing : redis-3.2.10-2.el7.x86_64                                    2/2 
  Verifying  : redis-3.2.10-2.el7.x86_64                                    1/2 
  Verifying  : jemalloc-3.6.0-1.el7.x86_64                                  2/2 

Installed:
  redis.x86_64 0:3.2.10-2.el7                                                   

Dependency Installed:
  jemalloc.x86_64 0:3.6.0-1.el7      
 Add the required repository before installing Sensu tool by creating a repo file named Sensu and enter the following content in the file. Save and exit the file. 

[root@linuxhelp ~]# vim /etc/yum.repos.d/sensu.repo

[sensu]
name=sensu-main
baseurl=http://repositories.sensuapp.org/yum/el/7/x86_64/
gpgcheck=0
enabled=1
The repo file has been created successfully created. Next install the Sensu tool by executing the following command and press y to continue with the installation process. 

[root@linuxhelp ~]# yum install sensu uchiwa -y
Loaded plugins: fastestmirror, langpacks
sensu                                                    | 2.5 kB     00:00     
sensu/primary_db                                           |  43 kB   00:00     
Loading mirror speeds from cached hostfile
 * base: centos.mirror.snu.edu.in
 * epel: mirror.ehost.vn
 * extras: centos.mirror.snu.edu.in
 * updates: centos.mirror.snu.edu.in
Resolving Dependencies
.
.
.
Installing : 1:sensu-0.26.5-2.x86_64                                      1/2 
  Installing : 1:uchiwa-0.22.0-1.x86_64                                     2/2 
  Verifying  : 1:uchiwa-0.22.0-1.x86_64                                     1/2 
  Verifying  : 1:sensu-0.26.5-2.x86_64                                      2/2 

Installed:
  sensu.x86_64 1:0.26.5-2                uchiwa.x86_64 1:0.22.0-1               

Complete!
Start and enable the Redis service. 

[root@linuxhelp ~]# systemctl start redis
[root@linuxhelp ~]# systemctl enable redis
ln -s '/usr/lib/systemd/system/redis.service' '/etc/systemd/system/multi-user.target.wants/redis.service'
Copy the .json file to the following location. 

[root@linuxhelp ~]# cp /etc/sensu/config.json.example /etc/sensu/config.json
Start and enable the following list of services. 

[root@linuxhelp ~]# systemctl start sensu-server
[root@linuxhelp ~]# systemctl start sensu-client
[root@linuxhelp ~]# systemctl start sensu-api
[root@linuxhelp ~]# systemctl start uchiwa


[root@linuxhelp ~]# systemctl enable sensu-server
sensu-server.service is not a native service, redirecting to /sbin/chkconfig.
Executing /sbin/chkconfig sensu-server on
The unit files have no [Install] section. They are not meant to be enabled
using systemctl.
Possible reasons for having this kind of units are:
1) A unit may be statically enabled by being symlinked from another unit's
   .wants/ or .requires/ directory.
2) A unit's purpose may be to act as a helper for some other unit which has
   a requirement dependency on it.
3) A unit may be started when needed via activation (socket, path, timer,
   D-Bus, udev, scripted systemctl call, ...).


[root@linuxhelp ~]# systemctl enable sensu-client
sensu-client.service is not a native service, redirecting to /sbin/chkconfig.
Executing /sbin/chkconfig sensu-client on
The unit files have no [Install] section. They are not meant to be enabled
using systemctl.
Possible reasons for having this kind of units are:
1) A unit may be statically enabled by being symlinked from another unit's
   .wants/ or .requires/ directory.
2) A unit's purpose may be to act as a helper for some other unit which has
   a requirement dependency on it.
3) A unit may be started when needed via activation (socket, path, timer,
   D-Bus, udev, scripted systemctl call, ...).

[root@linuxhelp ~]# systemctl enable sensu-api
sensu-api.service is not a native service, redirecting to /sbin/chkconfig.
Executing /sbin/chkconfig sensu-api on
The unit files have no [Install] section. They are not meant to be enabled
using systemctl.
Possible reasons for having this kind of units are:
1) A unit may be statically enabled by being symlinked from another unit's
   .wants/ or .requires/ directory.
2) A unit's purpose may be to act as a helper for some other unit which has
   a requirement dependency on it.
3) A unit may be started when needed via activation (socket, path, timer,
   D-Bus, udev, scripted systemctl call, ...).

[root@linuxhelp ~]# systemctl enable uchiwa
uchiwa.service is not a native service, redirecting to /sbin/chkconfig.
Executing /sbin/chkconfig uchiwa on
The unit files have no [Install] section. They are not meant to be enabled
using systemctl.
Possible reasons for having this kind of units are:
1) A unit may be statically enabled by being symlinked from another unit's
   .wants/ or .requires/ directory.
2) A unit's purpose may be to act as a helper for some other unit which has
   a requirement dependency on it.
3) A unit may be started when needed via activation (socket, path, timer,
   D-Bus, udev, scripted systemctl call, ...).

 
Set the Firewall configuration by executing the following set of commands.  

[root@linuxhelp ~]# firewall-cmd --add-port=3000/tcp
Success

[root@linuxhelp ~]# firewall-cmd --add-port=80/tcp
Success

[root@linuxhelp ~]# firewall-cmd --add-port=443/tcp
Success

[root@linuxhelp ~]# firewall-cmd --reload
success
This concludes the installation procedure of Sensu Monitoring tool on CentOS 7
