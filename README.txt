
This program runs the Sparta app on one vagrant virtual while another machine
runs the OWASP zed attack proxy program to run a fake attack on the app to discover
any vulnerabilities

to run the app:
- cd /home/ubuntu/app
- node app.js
this should have the app running on port 3000
use a browser with http://192.168.15.30:3000 to view the app

start a second terminal for the ZAP program

to run the ZAP program:
use this command to run the program
- sudo docker run -u zap -p 8080:8080 -p 8090:8090 -i owasp/zap2docker-stable zap-webswing.sh
then access it on the browser with http://192.168.8.16:8080/zap

when you reach the homepage click on "automated scan"
type in the url the app is running on (written above) and click attack
this should show the vulnerabilities on the app
