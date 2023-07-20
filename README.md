#SETUP SONAR USING DOCKER-COMPOSE

##Write configuration file:
sonar-project.properties

##Run the docker compose file
Using the docker-compose.yaml present in the repo.

##Create Project and Project token
1. Once you can access the console of Sonarqube at IP:9000, create a Project
2. Create a secret token for the project

docker compose up -d

##Source Code Loaction
Record the path where source code is kept

#Run the Sonar Scanner
The pod of sonar-scanner gets deployed, performs its operations and gets deleted
docker run \
    --rm \
    -e SONAR_HOST_URL="http://13.233.174.37:9000/" \
    -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=Node-test" \
    -e SONAR_LOGIN="sqp_53d5efec7e379cc01490f963ce18981ec69cd2a5" \
    -v "/home/ubuntu/sonarserver/src/nodejs-mongo-loginpage:/usr/src" \
    sonarsource/sonar-scanner-cli

Edit the values as per your project needs.
1. SONAR_HOST_URL=  The URL where console of Sonarqube is accessible
2. SONAR_SCANNER_OPTS= The project name

##Report
Once the report is generated, we can see it in console, under the project name. 
