
<!-- ABOUT THE PROJECT -->
## About The Project

This project was created to implement Filebeat on PfSense, mostly for the suricata service available on PfSense but you could use it for any other module present in Filebeat (syslog,apache..)

### Built With
I was able to make it work thanks to : 

Creating a freebsd service form source:
https://blog.securitybits.io/2019/12/beats-7.5.0-on-pfsense-2.4.4/


<!-- GETTING STARTED -->
## Getting Started
Upload the directory anywhere on your PfSense or freeBSD server.

### Prerequisites
None.


<!-- USAGE EXAMPLES -->
## Config

To make it work you'll have to update config, more precisely filebeat.yml :

setup.kibana:
  host: "IP"
  username: "xxx"
  password: "xxx"

and 

output.elasticsearch:
  hosts: ["IP"]
  protocol: "http"
  username: "xxx"
  password: "xxx"


## Run this bad boy

Setup the dashboards and index with :
./filebeat setup

Run it with:
./filebeat run &

How to debug:
./filebeat -e

Problems you may encouter:
Any prior install of a filebeat index may cause some problems on your kibana dashboard,
if it is the case i would recommend to delete all filebeat object installed on kibana and do ./filebeat setup   again.
