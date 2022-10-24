# python-crontab

## install 

````
pip install python-crontab
````

## test1.py

````
from datetime import datetime
import os
  
cwd=os.getcwd()
  
with open(os.path.join(cwd,"test.txt"),"a") as f:
    f.write("Accessed test1.py on " + str(datetime.now()) + "\n")
````    

## test2.py

````
from datetime import datetime
import os
  
cwd=os.getcwd()
  
with open(os.path.join(cwd,"test.txt"),"a") as f:
    f.write("Accessed test2.py on " + str(datetime.now()) + "\n")
````

## Final script 

````
from crontab import CronTab
  
cron=CronTab(user="aayussss2101")
  
job1=cron.new(command="python3 test1.py")
job1.minute.every(2)
  
job2=cron.new(command="python3 test2.py")
job2.minute.every(1)
  
cron.write()
````
