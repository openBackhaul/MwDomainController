# Interface Validator Script Steps


### Steps for  running interfaceValidator:

1.  Download the interfacevalidator script from github path locally `https://github.com/openBackhaul/equipment/tree/tsi/EquipmentAugment_1.1.0-tsi.240621.0815+validator`

2.  Two files will get downloaded in local.
`EquipmentAugment_1.1.0-tsi.240621.0815+validator.json , EquipmentAugment_1.1.0-tsi.240621.0815+data.json`
 
3. Edit the attributes (server, authorizationCode and mountName) in `EquipmentAugment_1.1.0-tsi.240621.0815+data.json` input file and save it.<br>
server			- Please enter controller-IP and port <br>
authorizationCode	- Please enter authorizationCode based on username and password<br>
mountName		- Please enter Node Name for which script needs to be executed ensure device is connected in  SDN-CONTROLLER <br>
For example :
```
		{
				"serverName": "controller",
				"server": "http://{SDN-CONTROLLER-IP}:8181", 
				"pathToControlConstruct": "/rests/data/network-topology:network-topology/topology=topology-netconf/node={mountName}/yang-ext:mount/core-model-1-4:control-construct",
				"authorizationCode": "Basic YWRtaW46YWRtaW4="
			}
		],
		"collectionInputList": [
			{
				"collectionName": "EquipmentAugment",
				"serverToBeApplied": "controller",
				"mountName": "xxxxxx"
			}
````

4. Ensure the postman version  `10.21.16`.

5. Import the `EquipmentAugment_1.1.0-tsi.240621.0815+validator.json` file from local to postman.

6. Try to run the collection by selecting  the input file as `EquipmentAugment_1.1.0-tsi.240621.0815+data.json` .


 
