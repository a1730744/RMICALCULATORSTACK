# RMICALCULATORSTACK 06.08.2023
The RMI (Remote Method Invocation) is an API that provides a mechanism to create distributed application in java. The RMI allows an object to invoke methods on an object running in another JVM.

The RMI provides remote communication between the applications using two objects stub and skeleton.
Understanding stub and skeleton
RMI uses stub and skeleton object for communication with the remote object.A remote object is an object whose method can be invoked from another JVM. Let's understand the stub and skeleton objects:
stub:
The stub is an object, acts as a gateway for the client side. All the outgoing requests are routed through it. It resides at the client side and represents the remote object. When the caller invokes method on the stub object, it does the following tasks:
It initiates a connection with remote Virtual Machine (JVM),
It writes and transmits (marshals) the parameters to the remote Virtual Machine (JVM),
It waits for the result
It reads (unmarshals) the return value or exception, and
It finally, returns the value to the caller.
skeleton:
The skeleton is an object, acts as a gateway for the server side object. All the incoming requests are routed through it. When the skeleton receives the incoming request, it does the following tasks:
It reads the parameter for the remote method
It invokes the method on the actual remote object, and
It writes and transmits (marshals) the result to the caller.
In the Java 2 SDK, an stub protocol was introduced that eliminates the need for

Understanding requirements for the distributed applications
If any application performs these tasks, it can be distributed application.
Java RMI Example
The is given the 6 steps to write the RMI program.

(Create the remote interface)
Provide the implementation of the remote interface(then add it to library jar file)
Compile the implementation class and create the stub and skeleton objects using the rmic tool
Start the registry service by rmiregistry tool
Create and start the remote application
Create and start the client application

1) create the remote interface
2) Provide the implementation of the remote interface
3) create the stub and skeleton objects using the rmic tool.(rmic functionin server Remote  )
4) Start the registry service by the rmiregistry tool(rmiregistry 5000  )
5) Create and run the server application
6) Create and run the client application

For running this rmi example:
  
1) compile all the java files  (javac *.java)
 
2)create stub and skeleton object by rmic tool  (rmic AdderRemote )
   
3)start rmi registry in one command prompt  (rmiregistry 5000)
   
4)start the server in another command prompt ( java MyServer  )

 
5)start the client application in another command prompt  (java MyClient )
  
*for connecting to server we must have the address that we can find it in more app such as netstat -a

We explain how to make RMI application with java that get number and count them over stack
