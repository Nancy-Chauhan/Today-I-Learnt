## TIL: 26-02-2021

DHCP Protocol is used to assign IP addresses. 
It is present in router and it is also used in  Docker, Kubernetes, AWS and etc.

- Docker:  By default, the container is assigned an IP address for every Docker network it connects to. The IP address is assigned from the pool assigned to the network, so the Docker daemon effectively acts as a DHCP server for each container.
 
## TIL: 07-03-2021

Idempotency: Idempotence is talked about a lot in the context of "RESTful" web services. Basically, if making multiple identical requests has the same effect as making a single request it is idempotency.
     
## TIL: 08-03-2021

Interface vs abstract class in Java 
- When to use what?
- Interfaces can be used if we want a full implementation and use abstract classes when you want partial pieces for your design. 

## TIL: 10-03-2021

- Problem : You are calling resource even when it is not needed which created the side effect like overriding in db. 
- Solution: Can be tackled by using supplier. This was due to incorrect usage of optional (https://www.baeldung.com/java-optional)
- Optional: orElse() and orElseGet(). orElse() takes concrete value and orElseGet() takes supplier. 
- Lazy Evaluation using supplier: You pass function(lambda) instead of concrete values. Whenever you need the value you call the supplier and it computes and 
then returns the value.

## TIL: 11-03-2021 
Came across CGI (common gateway Interface). CGI led to developmemt of WSGI, servlet
https://www.geeksforgeeks.org/common-gateway-interface-cgi/ 

## TIL: 15-03-2021

- Docker compose override : https://docs.docker.com/compose/extends/ 

Problem : Port forwarding, concurrent CI was portfowarding to localhost concurrently which led to `port already occupied issue`. 

Solution : With docker-compose override for CI, you will be using the docker virtual namespace only.

- tail -f /dev/null to run container indefinitely 

## TIL: 16-03-2021
Retry and Resiliency: 
Network calls are most likely to fail so putting retry on particular peice of code which is most likely to fail is the apt way.

## TIL: 18-03-2021
Database Transaction: A transaction is a unit of work that you want to treat as "a whole." It has to either happen in full or not at all. 

ACID = Atomicity, Consistency, Isolation, Durability 

## TIL: 24-03-2021

I have been recently working around CQRS. 
Command-Query Responsibility Separation or CQRS is a simple architectural paradigm. It dictates that we should separate our system in two conceptually different parts. There is the command side, also known as the write side, which changes the state of the system via updates, deletes, etc. and the query side or the read side which only queries the state (presenting the information to the user or other modules of the system). Will write a detailed blog on this. 

## TIL: 10-04-2021

Fan-In vs Fan-out: 
Fan-in refers to the number of higher-level modules that directly call the module, while fan-out refers to the number of lower-level modules directly called by the module 

- Fan in Example : Collect many tasks from smaller distribution points and combine them to larger tasks i.e courier system 

- One use case I can think of is fan-out write/read.

- For example, if you tweet and Twitter delivers that to all the subscribers feeds as soon as it is written (fan-out write). Or a feed service that waits until users are actually consuming the feed, at that time it looks for posts that have been written that this user is eligible to read (fan-out read). 


### How To Harden the Security of Your Production Django Project

https://www.digitalocean.com/community/tutorials/how-to-harden-your-production-django-project 

## TIL: 13-04-2021

SQLite strives to provide local data storage for individual applications and devices. SQLite is a good fit for use in cellphones, set-top boxes, televisions, game consoles, cameras, watches, kitchen appliances, thermostats, automobiles, machine tools, airplanes, remote sensors, drones, medical devices, and robots: the "internet of things". For device-local storage and testing use SQLite 

https://sqlite.org/whentouse.html 

## TIL: 14-04-2021

- I came across a cool tool for schema design: https://www.dbdesigner.net/ 
- Learnt about various Software devloper hacks for productivity (Will draft a blog on this) https://twitter.com/_nancychauhan/status/1382307259854716931 

## TIL: 16-04-2021

- Blog on Top 10 Productive Hacks for Software Developers : https://medium.com/@_nancychauhan/top-10-productive-hacks-for-software-developers-c0feb8ca8dab 
- Read amazing blog on How to Run Effective 1:1s https://refactoring.fm/p/how-to-run-effective-11s-?r=3dhy0&utm_campaign=post&utm_medium=email&utm_source=copy
- Good resource on `The Architecture of Open Source Applications`: http://aosabook.org/en/index.html 


## TIL: 20-04-2021

- How Serializers works in Django Rest Framework ?
- Reference: https://www.django-rest-framework.org/api-guide/serializers/
- MySQL root password change
```
SET PASSWORD FOR 'root'@'localhost' = PASSWORD('mypass');
FLUSH PRIVILEGES;
```

## TIL: 22-04-2021

- cron expressions: https://crontab.guru/#30*_*_*_* This is a good place for finding out cron schedule 
- https://medium.com/@yedjoe/celery-4-periodic-task-in-django-9f6b5a8c21c7 : Good reference for setting up Periodic task in django. You can create a 
cron scheduler with this for periodic tasks using celery beat (https://docs.celeryproject.org/en/stable/userguide/periodic-tasks.html#:~:text=celery%20beat%20is%20a%20scheduler,entries%20in%20a%20SQL%20database.)
- Celery Beat Schedule: 
```
from celery.schedules import crontab
# Other Celery settings
CELERY_BEAT_SCHEDULE = {
    'task-number-one': {
        'task': 'app1.tasks.task_number_one',
        'schedule': crontab(minute=59, hour=23),
        'args': (*args)
    },
    'task-number-two': {
        'task': 'app2.tasks.task_number_two',
        'schedule': crontab(minute=0, hour='*/3,10-19'),
        'args': (*args)
    }
}
```
## TIL: 24/04/2021

- Use webp instead of png and jpg/jpeg for hosting images in website. It improves the performance.
- Using webp I reduced download time of my website from 30 sec to 3 sec. 
- Use https://web.dev/measure/ to measure the site performance. It also gives the suggestion for improvement.

## TIL: 27/04/2021

- New blog: https://medium.com/@_nancychauhan/introduction-to-message-queue-build-a-newsletter-app-using-django-celery-and-rabbitmq-in-30-min-6d484162391d 

## TIL: 28/04/2021

- `watch -n 1 curl -vvv 192.168.64.3` Repeats the curl indefintely 
