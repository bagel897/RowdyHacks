#Commands to make stuff run
CAUTION: Written for Mac/Linux  
Step 1: Get into venv  
`source venv/bin/activate`  
from RowdyHacks(2)  
Step 2: Go to the app  
`cd app`
Step 3: Setup google cloud  
`gcloud auth application-default login`  
`curl -o cloud_sql_proxy https://dl.google.com/cloudsql/cloud_sql_proxy.darwin.amd64`
`chmod +x cloud_sql_proxy`
`./cloud_sql_proxy -instances="rowdyhacks-272516:us-central1:polls-instance"=tcp:3306`  
Step 4: Setup libraries  
`pip install -r requirements.txt`  
Step 4.5: Test on local  
`python manage.py makemigrations`   
`python manage.py makemigrations polls`    
`python manage.py migrate`  
`python manage.py runserver`

Step 5: Launch  
`python manage.py collectstatic`
`gcloud app deploy`

