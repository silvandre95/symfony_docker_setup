# Setup your Symfony application with Docker

## What do we need?
 - Install Docker Desktop

## What will you have?
 - PHP 8.2
 - MySql 8
 - Nginx Web Server
 - phpMyAdmin 5
 - XDebug

<br>

## Lets do it step by step:
- ### Clone this repository to your machine;
- ### Go to `php/Dockerfile` and change the git `email` and `name`;
- ### Go to `.env` and change the variable `PROJECT_NAME` (or just stay as it is);
- ### Now, run the `docker-compose.yml`
- ### Open a bash terminal in the php container that you have just created;
- ### Type `symfony check:requirements`; You must see a green message saying 'Your system is ready to run Symfony projects'.
- ### Run this command `composer create-project symfony/skeleton .`;
- ### Open your new Symfony application here [http://localhost:8080](http://localhost:8080);
- ### Open `phpMyAdmin` here [http://localhost:9005](http://localhost:9005);

<br>

## Done!
## Now you have your Symfony application working!