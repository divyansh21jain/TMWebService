# TMWebServiceFramework

TMWebServiceFramework is a simple, fast, versatile and highly-productive Web Services Framework.

The framework strictly follows J2EE specifications.

# Instructions to use framework:

1)Clone or download the repository to the webapps folder of your webservice.

2)Start webserver, after starting your webserver, if all things go well then you will see message as "Started Successfully" on your webserver window.

# Steps to create your own service

1)To create your own service you have to create a class and import the following package com.thinking.machines.school.annotations.*; .

2)To include your service as a framework part you will have to use @Path annotation on the class,method according to your architecture. In @Path annotation you must specify the url pattern in string format.

3)To send response you have to specify @ResponseType annotation on the method you can pass 3 values to it :
    a)text/html: to send html in response with a return type as a string.
    b)json:to send json in response with a return type as an object.
    c)none:to return nothing.

# For compiling the service:
 windows:

javac -classpath pathToYourWebserver/webapps/frameworkFolder/WEB-INF/classes;pathToYourWebserver/webapps/frameworkFolder/WEB-INF/lib/*;pathToYourWebserver/lib/*;. serviceFile.java

# For testing:

type following url in your browser:

    http://serverIP:serverPort/webappName/service/pathAnnotationValueClass/pathAnnotationValueMethod


# How to create a secured service:

1)Create a class & import package "com.thinking.machines.school.interfaces.*" which contains a interface named as AuthorizationInterface. Implement this interface in your class and use its methods. 

2)First method is boolean ifSecured(HttpSession,HttpServletRequest,ServletContext).

3)Second method is void ifUnAuthorized(HttpSession,HttpServletRequest,ServletContext)

4)Use @Secured in method and provide it with your class name.

# Other services we have:
  a) File upload:
	Use @RequiredFiles and pass it a file array
        
  b) Request Forwarding:
	Use @Forward annotation and specify the url/servlet/fileName to which you want the request to be forwarded.
        
  c)While using jars specify the jar file names against jars property of WEB-INF/conf/ServiceConfiguration.conf         

# note : -Only packages specified against scanPackage in WEB-INF/conf/ServiceConfiguration.config will be scanned , make sure that all the services created by you are located in the specified folder. 
