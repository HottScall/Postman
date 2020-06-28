<h1 align="center">Postman</h1>

Things covered in below tutorial:

- Creating API requests 
- Collections; what are they? Why use them? How to create them.
- Variables; what are they? Why use them? How to create them.


<h2 align="center">CREATING AN API REQUEST</h2>

<h3 align="center">HAVE YOUR API REQUEST READY</h3>

- In this example I googled (sample rest app request) and went on website https://reqres.in/ 
- Then I selected the GET request for SINGLE USER 
- Go to google/notepad/text editor and paste in the the web url https://reqres.in/ and append the get request end point, in this case  for SINGLE USER it’s - api/users?page=2
- Goggle is best as if you enter the entire api request correctly it should display the data as html in the browser 
- So complete request is https://reqres.in/api/users?page=2

 <h3 align="center">Creating a request</h3>	
 
- Create a new workspace (Give it a name and optional description)
- Create a new request in that workspace and give it a request name of your choice, optional description. Then add to existing collection or create a new collection. In this case create a new collection, then select that collection and save the request to the collection. 
- Now within your collection you can add your complete request to the GET request tab. Send it and it should return your data (this is for a simple get requests, other requests can be more complex so follow later in tutorial if request is more complex than a simple get request). 
- Remember to save your response once you have done something with it. 
	
<h4 align="center">IMPORTANT INFORMATION TO NOTE</h4>			

Above where the response to your request comes in is some important information:

- Status: You should be looking for 200, which is http request okay, look up http requests if you have anything other than 200.
- Time: How long it took to make the request and return the data 
- Size: Self explanatory, but if you hover over this tab you get the individual size of the body and the headers. 


<h2 align="center">COLLECTIONS</h2>

<h3 align="center">WHAT IS A COLLECTION </h3>					

A group of API requests where the API requests can be stored and saved in logical arrangements. Collections can allow you to add several addition parameters upon creation, for example if you are making multiple different api requests from a single API that requires an API key and password, a collection can store this information preventing you from continually adding this information every time you make a request. 

<h3 align="center">HOW TO CREATE COLLECTIONS</h3>		

New -> Collections -> Add details to make your collections. 

There a few features you can use in a collection such as sharing your collection with people, you can run a collection which runs all the requests inside your collection and you can also view the collection in a web browser. 

<h3 align="center">CREATING FOLDERS INSIDE COLLECTIONS</h3>			

Once you have a collection created you can create folders inside these within the options tab (…) An example for this, you can store all your GET requests in a single folder and all the POST requests in a separate folder. 

Collections form the basis for advanced operations in POSTMAN. 

<h3 align="center">HOW TO RUN A COLLECTION (COLLECTION RUNNER)</h3>

Once you have a collection of requests stored you can run them all in a single request. 

Click Collection -> Select the Options -> Select Run. A new window will open. 

Click the collection or specific folder you want to run (ensure that you can see your requests you want to run within your window pane on the left). 

You can select some additional information here, such as run within an Environment, how many iterations of the collection run you want to make, log the responses and others. 

Once you’re happy, select run and a new tab will open with details of the collection run. It will give you details an overview and all the passed and failed requests, but you can also select to view the successful and failed request separately.

You can run a high level overview by clicking Run Summary button. 

You can also go back to your previous page by clicking the collection runner. 

<h2 align="center">VARIABLES</h2>

<h3 align="center">What are variables?</h3>

The same as in coding, variables can be used as an element for data storage. 

<h3 align="center">Why use variables?</h3>>

So you can reuse those values at multiple places, like coding you can use variables to avoid repetition and to avoid having to redo work when values change, meaning if a value changes you only have to make the change at one location. 

<h3 align="center">Creating variables</h3>

Note that with your current Collection 1 that both the GET User request and GET UserList request both use the same initial URL  https://reqres.in/

Variables are created in Collections and Environment but NOT in specific folders. 

*NOTE* - Variables created within in Environment are now global variables. Be careful when setting these at Global Level. 

<h3 align="center">Creating and referring a variable in a collection</h3>

- Select the options tab (…) in the Collection or Folder 
- Click Edit 
- Select Variables 
- Add a name in the Variable Tab - Ensure there are no spaces at the end of your name and that you don’t add the / which appends the URL. 
- Add the variable value (URL in this case) in the initial value and save it
- Go to your requests, remove the initial URL value and add in your variable wrapped in double curly braces {{URL}}/here-is-the-rest-of-my-api-request

<h3 align="center">Creating and referring a variable in an Environment</h3>

- In the top right of the screen you have your Environment
- Select the settings tab 
- Click Globals 
- Follow the process above 
- For a quick view of what global variables you have within your Environment click on the eye next your Environment for a quick view of what Environment you have and what globals are set. 

 <h3 align="center">Useful tips for variables</h3>
 
If you have a variable within your collection but you want to view the value of that variable (say you forget or somebody has shared a collection with you and you’re viewing it for the first time). You can create a Postman console, which will return the entire value of the request when you click send. 

To get the Postman Console;

- Click Views
- Select Show Postman Console
- A new tab will open and when you run a request the full value of that request is stored in the console. 

 <h3 align="center">Getting and setting Variables through Scripts</h3>

- Open your console tab
- Select one of your requests
- Click on tests 
- Within here you can add your scripts
- You can log anything onto the console using console.log(“Hello”) which will print to the console when you run your test 

<h4 align="center">Getting a variable at a collection level</h4>

- pm.variables.get(“variableNameHere”)

You can now set this to a variable and console.log the value. 

Example:

let urlValue = pm.variables.get(“URL”)
console.log(“Value for URL is” + urlValue)

This will return your string plus the value of the URL variable which in this case is https://reqres.in/

<h4 align="center">Getting a variable at a Environment level</h4>

pm.globals.get(“addGlobalVarNameHere”)

OR 

pm.environment.get(“addGlobalVarNameHere”)

<h4 align="center">Setting a variable at collection level</h4>

To set a variable, you use the command: 
pm.variables.set(“name”, “POSTMAN”)

*NOTE* - Setting a variable takes a key, value pair. Name in this instance is the key whilst POSTMAN is the value

You can then call that using:

console.log(pm.variables.get(“name”))

Which returns: POSTMAN

*NOTE* - If you want to add scripts which run on every call to a script, you can select your collection, click edit, click pre-request scripts and add your scripts to the documentation bar below. 


