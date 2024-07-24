# Draft Version
**Pre-requisite:**
1. Start mediator application
2. Start Mediator instance manager and create device instance from vendor LAB 
 
**Steps to deploy controller and mount the devices:**
1. Pull the docker images which is an available in Docker Hub
2. Clone the below repo to start ODL ssh://git@dot-portal.de.pri.o2.com:2222/mw_sdn/packageartifacts/odl-controller.git
3. cd odl-controller/Templates/sdnr-deployment-configurations
4. Open and change the .env file with ODL version which is pulled in step-1
5. To start the container: docker-compose up -d
6. Please use below template to mount the devices
 
**URL:** http://<<ODLIP>>:8181/rests/data/network-topology:network-topology/topology=topology-netconf/node=<<nodename>>
 
**Operation:**
PUT
 
**Body:**
```
{
   "network-topology:node": [
       {
           "node-id": "<<nodename>>",
           "netconf-node-topology:sleep-factor": "2.5",
           "netconf-node-topology:max-connection-attempts": 8,
           "netconf-node-topology:username": "<<username>>",
           "netconf-node-topology:password": "<<password>>",
           "netconf-node-topology:default-request-timeout-millis": 1800000,
           "netconf-node-topology:schema-cache-directory": "<<schema_directory>>",
           "netconf-node-topology:between-attempts-timeout-millis": 5000,
           "netconf-node-topology:port": <<netconf_port>>,
           "netconf-node-topology:reconnect-on-changed-schema": false,
           "netconf-node-topology:tcp-only": false,
           "netconf-node-topology:keepalive-delay": 120,
           "netconf-node-topology:concurrent-rpc-limit": 0,
           "netconf-node-topology:host": "<<mediatror IP>>",
           "netconf-node-optional:notification": {
               "subscribe": true,
               "stream-name": "NETCONF"
           }
       }
   ]
}
```
