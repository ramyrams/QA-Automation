1. npm install -g newman
2. node -v
3. npm -v
4. newman run -h or C:\Users\a.rpalaniappan\AppData\Roaming\npm\newman.cmd


# Simple output in the console
C:\Users\a.rpalaniappan\AppData\Roaming\npm\newman.cmd run C:\PCEDDG\EddgEasyDemo_collection.json -e C:\PCEDDG\PC_EDDG.postman_environment.json --insecure 


# Avoid encodeing issue
C:\Users\a.rpalaniappan\AppData\Roaming\npm\newman.cmd run C:\PCEDDG\EddgEasyDemo_collection.json -e C:\PCEDDG\PC_EDDG.postman_environment.json --insecure --disable-unicode
https://medium.com/pacroy/how-to-fix-jenkins-console-log-encoding-issue-on-windows-a1f4b26e0db4


# This worked
C:\Users\a.rpalaniappan\AppData\Roaming\npm\newman.cmd run C:\PCEDDG\EddgEasyDemo_collection.json -e C:\PCEDDG\PC_EDDG.postman_environment.json --insecure -r htmlextra 

# Colored output in Jenkins
C:\Users\a.rpalaniappan\AppData\Roaming\npm\newman.cmd run C:\PCEDDG\EddgEasyDemo_collection.json -e C:\PCEDDG\PC_EDDG.postman_environment.json --insecure --disable-unicode -r cli,json,htmlextra --color on


C:\Users\a.rpalaniappan\AppData\Roaming\npm\newman.cmd run C:\PCEDDG\EddgEasyDemo_collection.json -e C:\PCEDDG\PC_EDDG.postman_environment.json --insecure --bail newman -x -r htmlextra 


# This one returns the detauk output in the CMD command prompt
newman run EddgEasyDemo_collection.json -e PC_EDDG.postman_environment.json

C:\Users\a.rpalaniappan\AppData\Roaming\npm\newman.cmd run C:\PCEDDG\EddgEasyDemo_collection.json -e C:\PCEDDG\PC_EDDG.postman_environment.json --insecure -r htmlextra 


Adding --no-color at the end of the command...

newman run "PE.postman_collection.json" --global-var "HEROKU_APP_NAME=$(Build.Data.Application)" --global-var "HEROKU_API_TOKEN=$(Library.DevOps.HerokuApiKey)" -r cli,junit,text --reporter-junit-export Test-Results.xml --reporter-text-export Test-Results.txt --disable-unicode --no-color
