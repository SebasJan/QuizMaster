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
[x] - Add public/private slider  
[x] - delete an entire quiz  
[x] - Wel echt /1 doen ipv query param  
[x] - Search doen op /quizzes en dan search param meegeven en dit checken in de controller  
[] - fix broken endpoints client side  
[] - Update an entire quiz client side  
[] - check each api call on client side for erros  
[] - Add search function to /choose page  
[] - style the login modal  
[] - style register page  
[] - Show the username of the person that made a public quiz     
[] - add some information on the homepage of the website   
[] - update audience and issuer to work on remote  
[] - change username and email    

[] - implement socket.io to play a quiz  
 
