# Serverless Django App
This project is a typical serverless architecture you can easily find from google.
I made this just for my records.
So I didn't add fancy front magic.

note: I used CDC API for covid distribution data
https://data.cdc.gov/resource/saz5-9hgg.json

#
## Zappa
Zappa is a system for running "serverless" Python web applications using AWS Lambda and AWS API Gateway. 
It handles all of the configuration and deployment automatically. 
To run it, it requires *zappa_settings.json*


### Reference
Zappa: https://github.com/Miserlou/Zappa


#
Do followings to run the django app:
setup virtual env: 
> virtualenv -p python venv

> source venv/bin/activate

> pip install -r requirements.txt

\
Create zappa_settings file
> zappa init

\
Add your own env file (see the template)
> vim .env

\
make sure your django server is running
> python manage.py runserver

\
go to 127.0.0.1 and see your portal is up

\
*Note: To use psycopg2, you need to use option -t to make extract lib in the project. 
> pip install psycopg2-binary -t .

However, if you use python version 3.7, you may need to copy the following files to the psycopg2 folder from https://github.com/jkehler/awslambda-psycopg2

* psycopg1.py

* _psycopg.cpython-37m-x86_64-linux-gnu.so


\
If your page is up run following command. It will give you new url
> zappa deploy dev

\
After the update your codes, the run 
> zappa update dev
