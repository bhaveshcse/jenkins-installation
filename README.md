## Jenkins installation on EC2 (Ubuntu)
# Installation of Java
Jenkins requires Java to run, yet not all Linux distributions include Java by default. Additionally, not all Java versions are compatible with Jenkins.
There are multiple Java implementations which you can use. OpenJDK is the most popular one at the moment, we will use it in this guide.
```bash
sudo apt update
sudo apt install -y fontconfig openjdk-17-jre
java -version
```
# Jenkins installation on EC2 (Ubuntu)
# Weekly release
A new release is produced weekly to deliver bug fixes and features to users and plugin developers. It can be installed from the debian apt repository.
```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install -y jenkins
```
# Long Term Support release
A LTS (Long-Term Support) release is chosen every 12 weeks from the stream of regular releases as the stable release for that time period. It can be installed from the debian-stable apt repository.
```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install -y jenkins
```
# Edit inbound rules in security group of EC2 
Allow traffic on port 8080

Create first username and password for jenkins and access.
