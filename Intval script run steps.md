# Interface Validator Script Steps


### Steps for  running interfaceValidator:

1.  Download the interfacevalidator script from github path locally `https://github.com/openBackhaul/equipment/tree/tsi/EquipmentAugment_1.1.0-tsi.240621.0815+validator`

2.  Two files will get downloaded in local.
`(EquipmentAugment_1.1.0-tsi.240621.0815+validator.json) (EquipmentAugment_1.1.0-tsi.240621.0815+data.json)`
 
3. Update the input file for attributes (server, authorizationCode and mountName) in EquipmentAugment_1.1.0-tsi.240621.0815+data.json file

For example :

```

{

				"serverName": "controller",

				"server": "http://xxxxxxx:xxxx", ##Please enter controller-IP and port ##

				"pathToControlConstruct": "/rests/data/network-topology:network-topology/topology=topology-netconf/node={mountName}/yang-ext:mount/core-model-1-4:control-construct",

				"authorizationCode": "xxxxxxxxx" ##Please enter authorizationCode based on username and password ##

			}

		],

		"collectionInputList": [

			{

				"collectionName": "EquipmentAugment",

				"serverToBeApplied": "controller",

				"mountName": "xxxxxx" ##Please enter Mountname for which script needs to be executed ensure device is Mounted in the controller ##

			}

````

4. After the changes save the (EquipmentAugment_1.1.0-tsi.240621.0815+data.json) file.

5. Ensure the postman version  `(10.21.16)`.

6. Import the `EquipmentAugment_1.1.0-tsi.240621.0815+validator.json` file from local to postman.

7. Try to run the collection by selecting  the input file as `EquipmentAugment_1.1.0-tsi.240621.0815+data.json` .


### data.json file :

```

[

	{

		"mode": "analysis",

		"serverList": [

			{

				"serverName": "dummy",

				"dummyUri": "ping.openBackhaul.com"

			},

			{

				"serverName": "mwdi",

				"server": "http://ip.add.re.ss:port",

				"pathToControlConstruct": "/core-model-1-4:network-control-domain=cache/control-construct={mountName}",

				"authorizationCode": "authorizationCode",

				"operationKey": "Operation key not yet provided.",

				"userName": "userName",

				"originator": "EquipmentAugment_1.1.0-tsi.240621.0815+validator",

				"xCorrelator": "00000000-0000-0000-0000-000000000532",

				"traceIndicator": "1",

				"customerJourney": ""

			},

			{

				"serverName": "controller",

				"server": "http://xxxxxxx:xxxx",

				"pathToControlConstruct": "/rests/data/network-topology:network-topology/topology=topology-netconf/node={mountName}/yang-ext:mount/core-model-1-4:control-construct",

				"authorizationCode": "xxxxxxxxx"

			}

		],

		"collectionInputList": [

			{

				"collectionName": "EquipmentAugment",

				"serverToBeApplied": "controller",

				"mountName": "xxxxxx"

			}

		]

	}

]


```
 