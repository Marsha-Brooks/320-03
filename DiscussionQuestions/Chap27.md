ISTA-320, Cohort 3 
C# Step by Step, Chapter 27 December 3, 2017
 1. Can a UWP app directly access a relational database by using technologies provided by Microsoft? Why or why not? 
No a UWP app cannot directly access a relational database using Microsoft technologies a third party platform is used to access data to make the apps easier to launch.  You don’t want your user to have to download a huge database to use with their app they purchased on the app store.  Not being able to access the relational database directly prevents dependencies to outside resources.
2. Describe how the Entity Framework works. 
The Entity Framework is a powerful technology with which you can connect to a relational database. It can reduce the amount of code that most developers need to write to add data access capabilities to an app. 

3. What is the difference between the code-first and the database-first approaches to developing UWP apps? 
Using the database-first  approach the Entity Framework generates classes based on the definitions of tables in the database. 
Using the code-first approach the Entity Framework generates tables based on the code.

4. What is a partial class? Why would we want to create partial classes?
A partial class is a class in which the code is split across one or more source files. You would want to create a partial class because it enables you to add your own code without the risk of having it accidentally overwritten if the Entity Framework code is  regenerated at some point in the future.
 5. Describe a RESTful web api. (Not in book.) Write a brief description of Representational State Transfer. What problem was it designed to solve? 
REST stands for ‘Representational State Transfer’ and it is an architectural pattern for creating an API that uses HTTP as its underlying communication method. 
The term API stands for ‘Application Programming Interface’. In the world of web development, the term ‘API’ is synonymous with online web services which client apps can use to retrieve and update data.
resources typically represent your data entities 
Representational State Transfer (REST) is a style of architecture based on a set of principles that describe how networked resources are defined and addressed.

The problems that REST was designed to resolve are 
1.State and functionality being divided into distributed resources
2. Uniquely addressing every resource using a uniform and minimal set of commands (typically using HTTP commands of GET, POST, PUT, or DELETE over the Internet)
3. Supporting caching, stateless, layered, client/server protocols

6. Give a brief description of the functionalities of these HTTP commands: GET, POST, PUT, DELETE
GET Retrieves the document specified in the URL property (use GetHeader to retrieve header information and GetChunk to get the rest of the information
POST Sends data to the server
PUT Replaces the page specified in the URL property with the specified data
DELETE deletes the specified resource
