# How to deploy your flask app for production ready on ec2.

## Prerequisites

1. Ubuntu Server
2. Flask App
3. Git Bash


## change host and port
```
if __name__ == "__main__":
    app.run(host="0.0.0.0",port=8001)
```
-> gunicorn must be in requirements.txt


## Update your Virtual Machine

```
sudo apt update && sudo apt upgrade -y
```

## Verify git and python installed
```
git -v && python3 --version
```

## Install git,python (if not installed)
```
sudo apt install git -y && sudo apt install python3 -y
```

## Clone your project on server

```
git clone "github project url"
```

## Move to project
```
cd "project directory"
```

## Install python virutal environemnt

```
sudo apt install -y python3.14-venv
```

## Intialize the virtual environment
```
python3 -m venv venv
```


## activate venv
```
source venv/bin/activate
```

## install packages and libraries
```
pip3 install -r requirements.txt
```


## run the python file using gunicorn
```
gunicorn --bind 0.0.0.0:8081 app:app
```
The first app is the python file name. 
The Second app is the variable name you used to intialize the flask app.

## allow the port 
```
sudo ufw allow <port no.>
```

Add port no to your inbound network security group.

# BOOM !! Your app is successfully deployed. :)
