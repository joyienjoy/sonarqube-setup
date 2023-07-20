#SETUP SONAR USING DOCKER-COMPOSE

Using the docker-compose.yaml present in the repo.

#Write configuration file:
sonar-project.properties

#Source Code Loaction
Record the path where source code is kept

#Create Project and Project token
1. Once you can access the console of Sonarqube at IP:9000, create a Project
2. Create a secret token for the project

#Run the Sonar Scanner
docker run \
    --rm \
    -e SONAR_HOST_URL="http://13.233.174.37:9000/" \
    -e SONAR_SCANNER_OPTS="-Dsonar.projectKey=Node-test" \
    -e SONAR_LOGIN="sqp_53d5efec7e379cc01490f963ce18981ec69cd2a5" \
    -v "/home/ubuntu/sonarserver/src/nodejs-mongo-loginpage:/usr/src" \
    sonarsource/sonar-scanner-cli

Edit the values as per your project needs.

#Report
Once the report is generated, we can see it in console. 
