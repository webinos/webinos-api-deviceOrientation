# webinos device orientation API #

**Service Type**: http://webinos.org/api/deviceorientation

The main concept of device orientation API is to display the physical orientation and motion of a hosting device.

The implementation is based on the [w3c specs](http://www.w3.org/TR/2011/WD-orientation-event-20111201/).


## Installation ##

To install the device orientation API you will need to npm the node module inside the webinos pzp.

For end users, you can simply open a command prompt in the root of your webinos-pzp and do: 

	npm install https://github.com/webinos/webinos-api-deviceOrientation.git

For developers that want to tweak the API, you should fork this repository and clone your fork inside the node_module of your pzp.

	cd node_modules
	git clone https://github.com/<your GitHub account>/webinos-api-deviceOrientation.git
	cd webinos-api-mediaplay
	npm install


## Getting a reference to the service ##

To discover the service you will have to search for the "http://webinos.org/api/deviceorientation" type. Example:

	var serviceType = "http://webinos.org/api/deviceorientation";
	webinos.discovery.findServices( new ServiceType(serviceType), 
		{ 
			onFound: serviceFoundFn, 
			onError: handleErrorFn
		}
	);
	function serviceFoundFn(service){
		// Do something with the service
	};
	function handleErrorFn(error){
		// Notify user
		console.log(error.message);
	}

Alternatively you can use the webinos dashboard to allow the user choose the device orientation API to use. Example:
 	
	webinos.dashboard.open({
         module:'explorer',
	     data:{
         	service:[
            	'http://webinos.org/api/deviceorientation'
         	],
            select:"services"
         }
     }).onAction(function successFn(data){
		  if (data.result.length > 0){
			// User selected some services
		  }
	 });

## Methods ##

Once you have a reference to an instance of a service you can use the following methods:

### addEventListener (type, listener, useCapture) 

Add a listener to the specified event.


### removeEventListener (type, listener, useCapture)

Remove the specifed event listener.
 

## Links ##

- [Specifications](http://www.w3.org/TR/2011/WD-orientation-event-20111201/)
- [Examples](https://github.com/webinos/webinos-api-deviceOrientation/wiki/Examples)

