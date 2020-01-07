
# Linux MySQL

User data:

sudo yum update -y
sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
sudo yum install -y httpd mariadb-server
sudo systemctl start httpd
sudo systemctl enable httpd

sudo systemctl start mariadb

"mysql_secure_installation <<EOF

y
secret
secret
y
y
y
y
EOF"

sudo systemctl enable mariadb

curl -l https://codeload.github.com/datacharmer/test_db/legacy.zip/master --output db.zip
unzip db.zip
cd *test_db*
mysql --user=root --password=secret < employees.sql
mysql --user=root --password=secret -t < test_employees_md5.sql

cd ..

curl -o ./aws-discovery-agent.tar.gz https://s3-us-west-2.amazonaws.com/aws-discovery-agent.us-west-2/linux/latest/aws-discovery-agent.tar.gz
tar -xzf aws-discovery-agent.tar.gz
sudo bash install -r us-west-2 -k <AWS key ID> -s <AWS key secret> #Can variableize? Paramter Store?

wget -O ./installer_linux.py https://console.cloudendure.com/installer_linux.py
sudo python ./installer_linux.py -t F330-BF5A-43D6-3AB3-8A13-3D0A-82FC-B237-A5A3-45FB-74E2-48EF-91D5-A0F7-545A-9537 --no-prompt

***

#PreReqs
-k AKIAQUM5QO57XP6SQF7Z -s SAwpq4BB3t8o+b9H+6AHcK3UEzdHKXANeMVLhMTi

Set Home region in Migration Hub
Set
Input Key and Secret into CloudEndure


CloudEndure
TCP
1500

***


### ADS
curl -o ./aws-discovery-agent.tar.gz https://s3-us-west-2.amazonaws.com/aws-discovery-agent.us-west-2/linux/latest/aws-discovery-agent.tar.gz
tar -xzf aws-discovery-agent.tar.gz
sudo bash install -r us-west-2 -k <AWS key ID> -s <AWS key secret>

### CloudEndure
Your Agent Installation Token:
414E-62D5-D9FE-3FC5-FDFE-96EA-C969-4C5F-D00A-D366-6F6D-584A-8B43-A390-7FD9-1A63

For Linux machines
Download the CloudEndure Agent Installer for Linux:
wget -O ./installer_linux.py https://console.cloudendure.com/installer_linux.py

Then run the Installer and follow the instructions:
sudo python ./installer_linux.py -t 414E-62D5-D9FE-3FC5-FDFE-96EA-C969-4C5F-D00A-D366-6F6D-584A-8B43-A390-7FD9-1A63 --no-prompt



***


# Windows servers


## ADS Agent

If outbound connections from your network are restricted, you'll need to update your firewall settings. Agents require access to arsenal over TCP port 443. They don't require any inbound ports to be open.

    For example, if your home region is us-west-2, you'd use https://arsenal.us-west-2.amazonaws.com:443

    Alternatively, if eu-central-1 is your home region, use with https://arsenal-discovery.eu-central-1.amazonaws.com:443

    Or substitute your home region as needed.

Access to AWS S3 in your home region is required for auto-upgrade to function.

Create an IAM user in the IAM console and attach the existing AWSApplicationDiscoveryAgentAccess permissions policy. This policy allows the user to perform necessary agent actions on your behalf. See Step 3: Provide Application Discovery Service Access to Non-Administrator Users by Attaching Policies for Discovery Agent installation prerequisites.

***

### CloudEndure

For Windows machines
Download the Agent Installer for Windows, then launch using this command:
installer_win.exe -t 414E-62D5-D9FE-3FC5-FDFE-96EA-C969-4C5F-D00A-D366-6F6D-584A-8B43-A390-7FD9-1A63 --no-prompt

***
