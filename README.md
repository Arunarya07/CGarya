# Sensu installation

Sensu is a free and open source monitoring solution that can be used to monitor server, application and various system services.
Sensu is written in Ruby that uses RabbitMQ to handle messages and Redis to store data. If you want to monitor your entire cloud environment, then Sensu may be a good option for you.


yum install epel-release -y
wget https://packages.erlang-solutions.com...
rpm -Uvh erlang-solutions-1.0-1.noarch.rpm
yum install erlang erlang-nox
wget https://www.rabbitmq.com/releases/rab...
rpm --import https://www.rabbitmq.com/rabbitmq-rel...
yum install rabbitmq-server
systemctl enable rabbitmq-server ; systemctl start rabbitmq-server

rabbitmqctl add_vhost /sensu
rabbitmqctl add_user sensu sensu
rabbitmqctl set_permissions -p /sensu sensu ".*" ".*" ".*"
nano /etc/yum.repos.d/sensu.repo
[sensu]
name=sensu-main
baseurl=http://repositories.sensuapp.org/yum/...
gpgcheck=0
enabled=1
yum install sensu uchiwa -y
cp /etc/sensu/config.json.example /etc/sensu/config.json
systemctl start sensu-server sensu-client sensu-api  uchiwa 
systemctl enable sensu-client sensu-api uchiwa sensu-server
firewall-cmd --permanent --zone=public --add-port=3000/tcp
firewall-cmd --reload
