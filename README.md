#Ryu with mininet vm

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
