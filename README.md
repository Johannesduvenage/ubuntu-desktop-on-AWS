# ubuntu-desktop-on-AWS
Setting up an Ubuntu Desktop GUI on AWS EC2

This lets you use Windows Remote Desktop Connection to connect to a Unbuntu Server running the xfce desktop.

My notes are derived from the instructions for Ubuntu 14.04LTS version: http://c-nergy.be/blog/?p=5305


1.  Launch an AWS instance. 
2.  Open the github bash and cd to the Desktop folder (where my AWS private key is located).
3.  Run the SSH command provided by the AWS EC2 management console website.

4.  Update the apt-get files.
```bash 
sudo apt-get update
```

5.  Create a user with a password so you can log-in using RDP.
```bash 
sudo adduser MyUsername
```

6.  Use the usermod command to add the user to the sudo group.
```bash 
sudo usermod -aG sudo MyUsername
```

7.  install the xfce4 desktop (the default ubuntu unity desktop doesn't seem to work).
```bash 
sudo apt-get install xfce4
```

8.  Install xrdp.
```bash 
sudo apt-get install xrdp
```

9.  Set xfce4 as the default user interface.
```bash echo xfce4-session >~/.xsession
sudo service xrdp restart
```

10.  Find you public IP address from the AWS console website.  Enter the IP address into Remote Desktop Connection application on your windows client machine and connect.  Enter your Ubuntu username and password to connect to the xfce desktop running on your AWS Ubuntu VM. 

