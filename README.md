# cs160

For developing unload their are some details that you need to know, for starters We used swift and Xcode for the front end Iphone interface, Express.js for the back end and MongoDB for the database. 

Front end specifics:
  Swift is used for front-end development, we have also imported pods such as Alomofire, AlamofireImage in order to collect images. After the back end server is up and running, simply download myUnloadIOS file and open the project on XCode. Make sure localhost number is same in both front end and back end. There are 2 controller classes for User and Item specifically and API calls are handled by the Service.swift class.


Back end specifics: 
  Back end is written in javascript using the express.js framework. The server launch file is index.js and can be launched with npm start if all the node dependenticies are there. It uses bycrypt, mongoose, body-parser and express. Mongoose is used to create the schema for the mongoDB collections of users and items
  
  Same with the 2 collections there are only 2 routes one for users and one for items.
   
   users routes and api:
    
    localhost:3000/users
    
    api: /users/signup - POST request: it will check if the sent body is empty, check if email is already in the DB, if its not then it salts the password and encrypts it and creates a new user with email and password in the DB. 
           
           /users/login - POST request: it checks if the email is in the DB, if it is then check if the passwords match, if so you are logged in, else it returns auth error. Note that it does not yet use tokens for authorizations.
           
           /users/:userId - DELETE request- if given an objectId of a user in the collection it will remove the user from the collection
 
 item route and api:
    
    localhost:3000/item
     
     api: /item - GET request: pulls all items in the collection.
         
         /item - POST request: creates and item object in the DB.
         
         /item/itemId - GET request: pulls up a specific item by it's ObjectId
         
         /item/itemId - PATCH request: does nothing, just filler for this leg of development.
         
         /item/itemId - DELETE request: When given an item's objectId it will remove the item from the DB collection
          

F.A.Q

  Users are able to securely login and signup into the system. No empty spaces allowed.
  
  Items does not carry picture function yet, it will be implemented soon.
  
  Different email per account
  
  Currenty cannot reset password
  
  Can only add an item
  
  Only an item name is required for an item listing at this implementation.
  
  Items weight must include units immediately after the weight, no spaces.
  
  Items dimensions are always in inches.
  
