 # Multitenancy 
 
 - Is the software acrhitecture pattern to run the same application instance for different customer (tenants) , 
 -  that means different customer will be using same application server ,  database or any other resource binded with application
   platform.
 - So every data will be in form of metadata (data inside data) .
 -  So creating a record in database for one user gives user same interface as others user will be getting , but in backend let say   
   unique id ( logical separation) has been generated for users and all the data user gonna create will be recorded under his/her unique instance as metadata.
-  So it gives logical separation than physical separation (single tenenancy) .

 -- challenges (as of now my understanding )  ?
 - Deciding the logic to generate unique id (private key ..)  or main controlling organization for users.	
 - which user & how it would be acessing the organization ?
 - giving user the access of a particular resource on demand , so tenant can also isolated resources as per demand.
    now providing low level isolation might lead to more complex code base (or can be handled by microservice architecture ?).
 - handling/ archving the APIs (mostly restful) as per tenant.
 - no data leaking from one to another .
 - If the single resources in which all tenants are dependent fails , all tenants suffer .
 - 3rd party identity provider &  library integration .


 -- advantages ?
 If any software update / bug fixes / version rolling 
 - all can be done in 1 application server , in one database or resource that will roll out to all instances seamlessly.
 - easily scalable 
 - single code base 
 - reduces infra cost , as sharing hardware resources.


--compared with ?
- Single tenancy : 
	so user can install the application in their own server and have 100 % control on how they work .
- multi-instance architecture 
- Virtulization 


some links :
 	https://www.youtube.com/watch?v=Kg_SHjp3DQ4 
 	https://www.youtube.com/watch?v=Tuy_O37H3O8  (multi tenancy in salesforce)
  	https://www.youtube.com/watch?v=WY1CWROPAU8 (good)


