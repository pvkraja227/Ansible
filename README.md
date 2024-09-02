Master

ssh-keygen\
cd .ssh\
cat id_ed25519.pub (copy)\
sudo su - root\
sudo su - ubuntu\

node1:\
cd .ssh\
vi authorized_keys\
paste\
sudo su - root\
sudo su - ubuntu\

node2:\
cd .ssh\
vi authorized_keys\
paste\
sudo su - root\
sudo su - ubuntu\

Master:

ssh ubuntu@node1IP (check)\
ssh ubuntu@node2IP (check)

Install Ansible

sudo apt update\
sudo apt install software-properties-common\
sudo add-apt-repository --yes --update ppa:ansible/ansible\
sudo apt install ansible -y\

ansible --version

sudo vi /etc/ansible/ansible.cfg\
add -> inventory= /etc/ansible/hosts - save\
ansible-config init --disabled -t all > ansible.cfg\

sudo vi /etc/ansible/hosts\
add -> [webservers]\
privateIP's of nodes - save\

ansible all -m ping (o/p: ping pong)







