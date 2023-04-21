# Introduction

This project contains some sample GitLab CI/CD pipelines that demonstrate different CI/CD features.

# Samples

## TotD

Tip of the Day service contains a script to be run with every login to a bash environment - linux server, WSL, etc.
It contains the actual tips files and the script. Both are deployed to remote hosts, either for user specific or host wide use. The pipeline build the service by "compiling" the tips files to simple enumerated versions, tests the script and deploys it to remote server.

## TotD version 2 instructions

install dependencies in the nodeapp folder with command
````
npm install
````
create .env file in the nodeapp folder with values:

````
DB_PORT=5432
DB_HOST=localhost
POSTGRES_USER=user
POSTGRES_PASSWORD=password
POSTGRES_DB=tips
````
to run the database in docker container run the following command in the root directory of the project
````
docker compose up
````
add data to the database by navigating to nodeapp/scrips and run command
````
node add_data_to_db.js
````
to start webserver run following command in the nodeapp folder
````
node app.js
````


endpoints

````
Get all tips (GET)
http://localhost:3000/getall

Delete tip by Id (DELETE)
http://localhost:3000/:tid/delete

Update tip by Id (PATCH)
http://localhost:3000/:tid/update

Get tip by Id (GET)
http://localhost:3000/:tid

Get tip by Id as plain text (GET) and can use any positive integer number as :tid value to fetch tip
http://localhost:3000/:tid/plain

Add new tip (POST)
http://localhost:3000/addtip
````

# Postman screenshots

<div align="center">
    <p>Get tip by Id endpoint </p>
    <img src="/screenshots/getbyid_endpoint.png" width="600px"</img>
    <p>Get tip by Id plain text endpoint</p>
    <img src="/screenshots/getbyidplaintext_endpoint.png" width="600px"</img>
    <p>Delete tip by Id endpoint</p>
    <img src="/screenshots/deletetipbyid_endpoint.png" width="600px"</img>
    <p>Update tip by Id endpoint</p>
    <img src="/screenshots/updatetipbyid_endpoint.png" width="600px"</img>
    <p>Get all tips</p>
    <img src="/screenshots/getall_endpoint.png" width="600px"</img>
    <p>Add new tip</p>
    <img src="/screenshots/addnewtip_endpoint.png" width="600px"</img>
</div>

# Running the frontend with database and backend

install dependencies in the client folder with command
````
npm install
````
start database in docker container by running the following command in the root directory of the project
````
docker compose up
````
add data to the database by navigating to nodeapp/scrips and run command
````
node add_data_to_db.js
````
to start webserver run following command in the nodeapp folder
````
node app.js
````
to start frontend run following command in the client folder
````
npm start
````
# Frontend screenshots

<div align="center">
    <p>Homepage View </p>
    <img src="/screenshots/frontend_homepage.png" width="600px"</img>
    <p>Add New Tip</p>
    <img src="/screenshots/frontend_addtip.png" width="600px"</img>
    <p>View Tips</p>
    <img src="/screenshots/frontend_viewtips.png" width="600px"</img>
    <p>Edit Tip</p>
    <img src="/screenshots/frontend_viewtips_edit.png" width="600px"</img>
</div>

# Links and References

* https://docs.gitlab.com/ee/ci/pipelines/
* https://docs.gitlab.com/ee/ci/ssh_keys/
* https://www.udemy.com/course/gitlab-ci-pipelines-ci-cd-and-devops-for-beginners/



