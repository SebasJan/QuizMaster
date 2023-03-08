# QuizMaster
## To Run application:
Add a .env file in \QuizMaster\server. This file contains the following:  
DB_HOST=""  
DB_USER=""  
DB_PASSWORD=""  
DB_NAME=""  
SALT="" (For encrypting passwords)  
JWT_KEY="" (Secret key to generate JWT tokens)  

(Instead of running the database with docker you can connect to another mysql database respectively)

To start this application run:  
\QuizMaster\database: docker compose up   
  
\QuizMaster\server: npm run dev  
\QuizMaster\client: npm run dev  

## Notes:
TRUNCATE options;  
TRUNCATE questions;  
TRUNCATE quizzes;  

## TODO:
[] - fix bug that says not all fields are filled in, but they are. Maby a space?  
[] - update audience and issuer to work on remote
[] - Add search function to /choose page
[] - Update an entire quiz  
[] - delete an entire quiz  
[] - Upload and display an image  
[] - style the login modal  
[] - style register page  
[] - Show the username of the person that made a public quiz     
[] - add some information on the homepage of the website   
[] - change username and email    

[] - implement socket.io to play a quiz  
 
