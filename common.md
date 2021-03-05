
## #1. What is Node.js? Where can you use it?
Node.js is an open-source, cross-platform JavaScript runtime environment build on Chrome V8 engine

## #2. How does Node.js work?
Clients send requests to the webserver to interact with the web application. Requests can be non-blocking or blocking:
Querying for data
Deleting data 
Updating the data
Node.js retrieves the incoming requests and adds those to the Event Queue
The requests are then passed one-by-one through the Event Loop. It checks if the requests are simple enough not to require any external resources
The Event Loop processes simple requests (non-blocking operations), such as I/O Polling, and returns the responses to the corresponding clients


## #2.How is Node.js most frequently used?
Real-time chats
Internet of Things
Complex SPAs (Single-Page Applications)
Real-time collaboration tools
Streaming applications
Microservices architecture

## #2.Why is Node.js Single-threaded?
Node.js is single-threaded for async processing. By doing async processing on a single-thread under typical web loads, more performance and scalability


## #3.How would you define the term I/O? 

The term I/O is used to describe any program, operation, or device that transfers data from medium to another medium

----
## #.Vue lifecycle
i.Creation( Initialization ): Creation hoooks allow you to perfom action before your component has been added into the DOM. This hook run during server side rendering:

a: beforeCeated
b: Created
ii.Mounting (DOM insertion): They allow you to access your component immediately before and after first render

a: beforeMounted
b: Mounted
iii.Updating(Diff and re-render) Updating hooks are called when your reactive property used by your component change or something else causes it to re-render

beforeUpdate
updated
iv.Destruction(Teardown) They allow you to perfome action when you component is destroyed

beforeDestroy
destroyed

----
## #My SQL 
Is opensource database management system. It's fast and easy to use

Default port 3306

SELECT to select something from the table
INSERT to insert new record into table
UPDATE to update the existing record in the table
DELETE to delete existing record
INNER JOIN tot select record that have matching value in both table

----
## #Cold Fusion
ColdFusion is one of the easiest programming environments to use, and enables you to create powerful server-side web applications very quickly, with much less code than other technologies such as ASP, PHP, etc.

ColdFusion consists of two main elements:

A ColdFusion server (which runs on top of your web server),
ColdFusion templates (or files), which you write using ColdFusion Markup Language (CFML).
