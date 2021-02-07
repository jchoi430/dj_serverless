# dj_serverless

## Zappa
Zappa is a system for running "serverless" Python web applications using AWS Lambda and AWS API Gateway. 
It handles all of the configuartion and deployment automatically. 
To run it, it requires *zappa_settings.json*

Reference: https://github.com/Miserlou/Zappa


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
If your page is up run following command. It will give you new url
> zappa deploy dev

\
After the update your codes, the run 
> zappa update dev
#


## That's it, have fun!
#