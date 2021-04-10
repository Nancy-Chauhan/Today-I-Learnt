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
