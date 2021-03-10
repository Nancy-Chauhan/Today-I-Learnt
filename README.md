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

## TIL: 11-03-2021

- Problem : You are calling resource even when it is not needed which created the side effect like overriding in db. 
- Solution: Can be tackled by using supplier. This was due to incorrect usage of optional (https://www.baeldung.com/java-optional)
- Optional: orElse() and orElseGet(). orElse() takes concrete value and orElseGet() takes supplier. 
- Lazy Evaluation using supplier: You pass function(lambda) instead of concrete values. Whenever you need the value you call the supplier and it computes and 
then returns the value.
