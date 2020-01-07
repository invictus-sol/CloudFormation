## User Data


### All servers
curl -o ./aws-discovery-agent.tar.gz https://s3-us-west-2.amazonaws.com/aws-discovery-agent.us-west-2/linux/latest/aws-discovery-agent.tar.gz
tar -xzf aws-discovery-agent.tar.gz
sudo bash install -r us-west-2 -k <AWS key ID> -s <AWS key secret>


### MySQL
https://codeload.github.com/datacharmer/test_db/legacy.zip/master
unzip test_db-master.zip
cd test_db-master/

Edit the employees.sql file and adjust the comments to choose a different storage engine:

  set storage_engine = InnoDB;
-- set storage_engine = MyISAM;
-- set storage_engine = Falcon;
-- set storage_engine = PBXT;
-- set storage_engine = Maria;

mysql < employees.sql
