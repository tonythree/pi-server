# pi-server
pi-server is a raspberry-pi lightweight flask application that serves a real-time video streaming from raspberry pi camera and detect humans in real time using opencv library.

## Preliminary steps - install NGINX webserver
Before using a flask app, you should have a webserver installed like nginx or apache. I like nginx, but feel free to use apache. Do not use/install both, as you might experience the two webservers fighting for ports :D. Installing nginx is easy, open up the terminal and run these commands, one after the other:
```
sudo apt-get update
sudo apt-get install nginx
````
Verify the installation:
```
sudo nginx -v
````
Run nginx:
```
service nginx start
```
Verify nginx is running properly:
```
service nginx status
```
You should see Active: active (running) in green.


## Setup pi-server in Raspberry Pi (raspbian)
Create a python virtual environment using pipenv or venv and install requirements.txt: 
Using venv (tested and working):
```
cd spg50
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
```
Using pipenv:
```
cd spg50
pipenv shell
pipenv install -r requirements.txt
```

## Run flask application and access from raspberry
Everything is ready, now run:
```
python webstreaming.py --ip 0.0.0.0 --port 8000
```
Open your raspberry pi chromium browser and put into the browser:
```
0.0.0.0:8000
```

## Access real-time Raspberry Pi camera streaming from your computer.
Try to access to your raspberry pi from your own computer. In order for this to work, Computer and Raspberry should be connected to the same wi-fi network. First, copy the IP of your raspberry (in my case is 192.168.1.38), and then put in the browser:
```
192.168.1.38:8000
```
