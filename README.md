# Django_celery_examples
used in redis 
#used in celery
#django
#python
#use in different celery method that used to create a task enqueqe in fifo[first in first out ]method
#used in celery worker that help to run task in background in project
celery -A project_name worker -l info

#used in celery_beat that used to schedule advanced label task
celery -A project_name beat -l info

#used in different types of beat schedule method1
1=schedule[only for seconds]
2=crontab[used in minutes months day and year
3=solor=it is used to sunrise and sunset]
4=#it it used for periodic task 
import json

from datetime import datetime, timedelta

PeriodicTask.objects.create(

    interval=schedule,                  # we created this above.

    name='Importing contacts',          # simply describes this periodic task.

    task='proj.tasks.import_contacts',  # name of task.

    args=json.dumps(['arg1', 'arg2']),

    kwargs=json.dumps({

       'be_careful': True,

    }),

    expires=datetime.utcnow() + timedelta(seconds=30)

)
5=intervals
