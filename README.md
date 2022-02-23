#! /bin/bash
#Description: Installing the sonarqube on centos7
#Author: Terence
#Date: 2/2/22


echo "installation of sonarqube packages in progress..."
sleep 2
su - vagrant
echo "java installation"
sleep 3
sudo yum update -y
sudo yum install java-11-openjdk-devel -y
sudo yum install java-11-openjdk -y
sleep 2
echo "dowloading sonarqube"
cd /opt
sudo yum install wget -y
sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.3.0.51899.zip
echo "package extraction"
sudo yum install unzip -y
sudo unzip /opt/sonarqube-9.3.0.51899.zip
sudo chown -R vagrant:vagrant /opt/sonarqube-9.3.0.51899
cd /opt/sonarqube-9.3.0.51899/bin/linux-x86-64
./sonar.sh start