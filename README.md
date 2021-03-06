# MMM-WindyV2

### INTRODUCTION
This is a module for [MagicMirror](https://github.com/MichMich/MagicMirror) that adds the [Windy](https://www.windy.com/) weather map and was originally written by santi4488 as [MMM-windy](https://github.com/santi4488/MMM-windy). This is an extensive re-write that adds several new options, like adding your Lat & Lon to center on your location, setting zoom level and most importantly - adding the layer your prefer to see. You can choose from: wind, rain, clouds, temperature, pressure, currents and waves (free version). Further it now has support for voice control through [MMM-VoiceControlMe](https://github.com/Mykle1/MMM-VoiceControlMe) :)

Enjoy!

![alt text](https://github.com/TheStigh/MMM-WindyV2/blob/master/windy.gif)

#### UPDATE 03.03.2019:
- Added option for multiple layers to rotate with time interval

#### UPDATE 06.03.2019:
- Added support for voice control by MMM-VoiceControlMe
	- Can change between overlays
	- Can zoom in & out
	- At certain zoom level you get streets rather than just colors
	
#### UPDATE 07.03.2019:
- Added css to show weatherscale data in lower right corner
- Added support for different metrics

#### UPDATE 09.03.2019:
- Added support for play weather animation by voice control
- Added support for retaining zoom level between changing layers
- CSS cleanups
- Bugfixes

... commands for voice are at the bottom of this Readme

### TO-DO:
- Add support for voice control from MMM-AssistantMk2

### CONFIGURATION
You will need to get your own API key which can be obtained [here](https://api4.windy.com/api-key).
To use the module, add the following to the modules array in your `config/config.js` file:
```
{
	  module: "MMM-WindyV2",
	  position: 'fullscreen_above',          // this must be set to 'fullscreen_above'
	    config: {
		apiKey: 'YOUR API KEY',		 // insert your free or paid API key here
        	initLoadDelay: 50,               // optional, default is 50 milliseconds
	      	latitude: YOUR LATITUDE,         // example: 69.123
	        longitude: YOUR LONGITUDE,       // example: 17.123
	        zoomLevel: 6,                    // set your preferred zoom level
	        showLayer: 'rain',		 // wind, rain, clouds, temp, pressure, currents, waves
		rotateLayers: false,		 // set to true to rotate layers
		layersToRotate: ['wind','rain'], // layers to rotate
		delayRotate: 5000,		 // delay between rotated layers, in milliseconds
		wMinZoom: 3,			 // set minimum zoom level for WindyV2
		wMaxZoom: 17,			 // set maximum zoom level for WindyV2
		windyMetric: 'm/s',		 // 'kt', 'bft', 'm/s', 'km/h' and 'mph'
		updateTimer: 60 * 60 * 1000 * 6, // update per 6 hours
		retainZoom: true		 // retain zoomlevel between changing overlays
      }
},
```

### VOICE-CONTROL SUPPORTED
You want to voice-control Windy, you say? 
Go to [MMM-VoiceControlMe](https://github.com/Mykle1/MMM-VoiceControlMe) and follow instructions to install.
Commands to control MMM-WindyV2 are:
- show me rain
- show me temperature
- show me pressure
- show me currents
- show me waves
- show me wind
- zoom in
- zoom out
- Show default zoom	// shortcut to go back to default zoom from config.js
- Rotate layer		// start the rotation if set to true and changed zoom level
- Play animation        
- Cancel animation
