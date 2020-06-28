<h1 align="center">Postman</h1>
My notes from learning how to use postman 


<h2 align="center">CREATING AN API REQUEST</h2>

HAVE YOUR API REQUEST READY

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

