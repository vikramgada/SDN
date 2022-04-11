# ODL
sudo apt install openjdk-8-jdk openjdk-8-jre

java -version

Setup JAVA_HOME and JRE_HOME Variable

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

export JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre

Step 2 : STEP 2: Download distribution-karaf-0.6.0-Carbon.zip and unzip it Move to the directory distribution-karaf-0.6.0-Carbon and type: ./bin/karaf
feature:install odl-dlux-core

feature:install odl-dluxapps-nodes

feature:install odl-dluxapps-topology

feature:install odl-dluxapps-yangui

feature:install odl-dluxapps-yangvisualizer

feature:install odl-dluxapps-yangman

feature:install odl-l2switch-all

feature:install odl-restconf odl-l2switch-switch odl-mdsal-apidocs 

feature:install odl-l2switch-all odl-l2switch-switch-ui

feature install odl-vtn-manager-neutron odl-neutron-service odl-neutron-hostconfig-ovs

feature:install odl-ovsdb-library odl-restconf-all odl-ovsdb-southbound-api odl-ovsdb-southbound-impl odl-ovsdb-southbound-impl-rest

ODL
controller at URL http://localhost:8181/index.html
Default Password is admin admin

OVS

sudo /etc/init.d/openvswitch-switch start

sudo /etc/init.d/openvswitch-switch status

sudo ovs-vsctl show

sudo apt-get install openvswitch-switch

sudo apt install net-tools

netstat -a | grep 6653

netstat -a | grep 6640

ip r

sudo ovs-vsctl set-manager tcp:192.168.101.128 :6640  (give ip of ubuntu)

sudo ovs-vsctl show

Adding bridge

sudo ovs-vsctl add-br br0

sudo ovs-vsctl set-fail-mode br0 secure

ifconfig(my eth is ens33)

sudo ovs-vsctl add-port br0 ens33

sudo ovs-vsctl show

sudo ovs-vsctl set-controller br0 tcp:192.168.101.128:6653

sudo ovs-vsctl show

sudo ovs-ofctl show br0 -OOpenFlow13

controller at URL http://localhost:8181/index.html

# wireshark
sudo add-apt-repository universe

sudo apt install wireshark

If your wireshark start option is not enable do :
sudo dpkg-reconfigure wireshark-common

sudo chmod +x /usr/bin/dumpcap

# batch script eg
https://www.log2base2.com/shell-script-examples/loop/shell-script-to-find-factorial-of-a-number.html
# Ryu with mininet vm

sudo apt-get install git

sudo apt-get -y install git python3-pip python3-dev

python3 --version

pip3 --version

sudo apt-get -y install python3-eventlet python3-routes python3-webob python3-paramiko

mkdir sdn

cd sdn/

git clone --depth=1 https://github.com/osrg/ryu.git

cd ryu/

sudo pip3 install setuptools --upgrade

sudo python3 ./setup.py install

sudo pip3 install six --upgrade

sudo pip3 install oslo.config msgpack-python

sudo pip3 install eventlet --upgrade

sudo pip3 install -r tools/pip-requires

ryu-manager --version

sudo python3 setup.py install  ( Do if you are not able to view ryu-manager)

ryu-manager --version

ryu-manager --observe-links ryu.app.simple_switch ryu.app.gui_topology.gui_topology 

mininet steps

download VM https://github.com/mininet/mininet/releases/ 

Step 2: Open OVF file in the workstation.
Open new terminal in ubuntu

ssh -X mininet@192.168.142.130

Above IP address is of mininet
if the authority error exists then type
ssh -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no -X mininet@192.168.142.130

sudo mn --controller=remote,ip=192.168.142.131 --topo tree,depth=3

In above command ip is of ubuntu machine you can get by command  ip r    (  do  in new terminal to get the ip) 

# ONOS

sudo apt install openjdk-8-jdk openjdk-8-jre

java -version

sudo nano /etc/environment

Type in the first line

JAVA_HOME=”/usr/lib/jvm/java-8-openjdk-amd64”

JRE_HOME=”/usr/lib/jvm/java-8-openjdk-amd64/jre”

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

export JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre

unzip onos-1.12.0.zip

cd onos-1.12.0/

cd bin

ls

./onos-service 


Go to browser in localhost:8181/onos/ui/index.html
username - onos
Password - rocks 


# Floodlight
ls

unzip floodlight-20220410T130507Z-001.zip 

sudo apt install openjdk-8-jdk openjdk-8-jre

sudo nano /etc/environment

JAVA_HOME=”/usr/lib/jvm/java-8-openjdk-amd64”

JRE_HOME=”/usr/lib/jvm/java-8-openjdk-amd64/jre”

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

export JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre

sudo apt install ant

ant

sudo mkdir /var/lib/floodlight

sudo chmod 777 /var/lib/floodlight

java -jar target/floodlight.jar

Don’t close the running of jar And Open new terminal for mininet connect to mininet vm.

ssh -X mininet@192.168.142.130

sudo mn --controller=remote,ip=192.168.142.128 --topo=single,3

pingall

The ip address of the above remote if your ubuntu machine ip You have to open a 3rd terminal (new terminal) and wite ip r

http://localhost:8080/ui/index.html

