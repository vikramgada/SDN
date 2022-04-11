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

