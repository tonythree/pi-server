# pi-server
pi-server is a lightweight webserver flask application for raspberry pi that servers a real-time video streaming from raspberry pi camera.

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
python webstreaming.py --ip 0.0.0.0 --port 8000
```
Using pipenv:
```
cd spg50
pipenv shell
pipenv install -r requirements.txt
```
