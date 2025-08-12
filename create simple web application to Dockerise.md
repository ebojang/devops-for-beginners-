first check python version
python3 --version 
install flask 
==Flask is a simple and lightweight framework for creating web applications in python.== 
run 
~ pip3 install flask 
create a new directory under your repository, cd into it and create an application example app.py 
touch app.py
application code 

1) first we import the flask ( from flask import Flask) - this helps in creating a new flask application instance.
2) set a route (@app.route('/') - **We define a route for the root URL which is forward slash**
3) when someone visits the url (==@app.route('/')== the hello_world function is called (def hello_world(). which in return gives back ""i am a king!"
4) application is then run by using app.run
5) variable is used here to run application on our local host which is 0.0.0.0 and using port 5000. this allows us to look at local host 5000 for this application.

```python
from flask import Flask



app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'I am a king!'

if  __name__ == '__main__':
    app.run(host='0.0.0.0', port=5002)
```
once template or python file above is saved, run:
❯ python3 app.py
 * Serving Flask app 'app'
 * Debug mode: off
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5002
 * Running on http://172.20.162.206:5002
The above shows the service Flask app is running on the local host 127.0.0.1:5002

press ctrl c to stop the above link and refresh edge browser to confirm app stopped running