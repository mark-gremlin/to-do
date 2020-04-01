# to-do
Demo app that sets up a single spring boot service and integrates ALFI

# Prerequisities
* valid team certificate at `~/.gremlin/cert.pem`.  You can change this path, but you then need to expose it to Docker via docker-compose.yml
* valid team private key at `~/.gremlin/priv.pem`.  You can change this path, but you then need to expose it to Docker via docker-compose.yml
* export `SPRING_PROFILES_ACTIVE=dev`
* export `DB_PWD=EUPQItbKbHg8EGxZ`. For build simplicity sake, I'll let you connect to my Atlas sandbox.
* export `GREMLIN_TEAM_ID=<xxx>` - this is the Gremlin team ID, which you can get from the Gremlin UI

# Steps to get running
* `./mvn clean package` - this will build the JARs 
* `docker-compose build` - this will turn the JARs into Docker images locally
* `docker-compose up` - this will start all of the Docker images

# How to use
* Once you've got the system running, confirm that you've got 1 containers using `docker ps`.  You should see a to-do_todo_1
* Once the to-do application has finished starting up, you can make a request to the API at: `http://localhost:8080/all`
* You can create a new to-do with hardcoded values by right clicking on the `createToDo.http` file and selecting the `run` option. This result in a newly created todo record in the mongodb Atlas database.