# REACT-JS-DEPLOYMENTS

## REACT-JS-ON-NGINX-SERVER

* #### For this we need to have the dist files, go there where the files are located and open command prompt:
```bash
 cd dist
```
* #### Now archive all these file by following command:
```bash
 zip -r * distfiles.zip
```
* #### Now we need to move all these files to remote machince where we want to host this application.

* #### For that we need to run below command to copy that zip file to remote location:
```bash
 scp -i <privatekey.pem> <filename> ubuntu@<ipaddress>:/home/ubuntu
```
* #### Now we copied our zip file to remote machine now we need to ssh (login) to that machine:
```bash
 ssh -i <privatekey.pem> ubuntu@<ipaddress>
```
* #### First run the below command :
```bash
 sudo apt update
```
* #### Now we need to install unzip command to unzip the zip file which we have copied earlier:
```bash
 sudo apt install unzip -y
```
* #### Now unzip the files by following command :
```bash
 sudo unzip <distfiles.zip>
```
* #### Now we need to install nginx server:
```bash
 sudo apt install nginx -y
```
* #### Next need to check it installed or not :
```bash
 sudo nginx -v
```
* #### Now need to check whether nginx service is running or not:
```bash
 sudo systemctl status nginx
```
* ### NOTE: Make sure you need to enable 80 port on security groups on AWS.
* #### Now you can access the nginx default page by hitting public ip address on the browser:
```bash
 https://<ipaddress>
```
* #### Now get into the dist files directory:
```bash
 cd dist
```
* #### Now we need to move/copy all the files to target path:
```bash
 sudo cp -R * /var/www/html
```
* #### Now we need to restart the nginx server:
```bash
 sudo systemctl restart nginx
```
* #### Now you can access your react application by hitting public ip address on browser:
```bash
 http://<ipaddress>
```
