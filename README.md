
## Open Stack

## Installing OpenStack in ubuntu using MicroStack 
```
sudo snap install microstack --beta
```

![image](https://github.com/user-attachments/assets/49a54eff-50dd-4fbb-a8a0-a8fe15a2788d)


### 1. Initialize MicroStack
```
sudo microstack init --auto --control
```
This command:

* Sets up OpenStack services.
* Configures networking.
* Enables an internal bridge for virtual machines.

![image](https://github.com/user-attachments/assets/9c44ce63-ba00-45d2-b3da-ba6bd526be37)




### 3. Access OpenStack Dashboard
Once initialized, you can access the Horizon web dashboard:

-> Find the dashboard IP address:
```
ip a | grep inet
```
for example:-

![image](https://github.com/user-attachments/assets/1b8a63c3-717e-4811-b8d0-9abc4ea86a7a)



-> for password 
```
sudo snap get microstack config.credentials.keystone-password
```

-Go to web browser and search this above IP address:
```
http://<your-ip>:80
```

![image](https://github.com/user-attachments/assets/1901f1f6-87b5-4eb6-83a1-e15a28cbbdd5)



## Log in using the default credentials:

* Username: admin
* password: (from above)
![image](https://github.com/user-attachments/assets/2bb16b81-5fed-4612-b765-cc5439e2da54)

## Start Keystone Service
```
sudo apt install keystone -y
sudo systemctl list-units --type=service | grep keystone

```

![image](https://github.com/user-attachments/assets/a270c8f4-26ca-49ae-a28b-4bb9cfda43a5)


## Check if services are working correctly
To check if the services we have deployed are working correctly we will first install openstack Client use this command
```
sudo apt install -y python3-openstackclient
```
Verify installation using
```
openstack --version
```
![image](https://github.com/user-attachments/assets/9828b8f9-12cc-4ba1-abac-6eb5f2da5d16)

Check Services using
```
openstack compute service list
```
