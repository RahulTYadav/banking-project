Create a ubuntu machine 
sudo su
wget https://raw.githubusercontent.com/akshu20791/Deployment-script/main/jenkins.sh
ls
chmod 777 jenkins.sh
ls
./jenkins.sh
 apt install docker.io -y
 service docker start
sudo usermod -aG docker $USER
service jenkins restart
 sudo usermod -aG docker jenkins
 service jenkins restart


 Go to jenkins -> create pipeline and select https://github.com/alekhya167/star-agile-banking-finance/ as source code project
