- Install `Docker`, `docker-compose` and `terraform` on the `Jenkins server`.

## Docker CE and DOcker-compose install
```bash
sudo yum update -y
amazon-linux-extras install docker -y
systemctl start docker
systemctl enable docker
usermod -a -G docker ec2-user
usermod -a -G docker jenkins

sudo curl -L https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
yum -y install terraform
```

- Create a `Role` about `AmazonEC2FullAccess` on the `Jenkins Server`. Go `Action > Security > Modify IAM Role` and attach role `AmazonEC2FullAccess`.