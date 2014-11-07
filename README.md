freeboard-mqtt
==============

MQTT and IBM IoT Foundation plugins for freeboard.io

To use these plugins with your own copy of freeboard copy the files into a directory where freeboard will be able to see them, such as plugins/thirdparty in the freeboard main directory.

You will also need a copy of the [paho mqtt javascript library](http://eclipse.org/paho/clients/js/) and will need to insert the link to it into the following sections in the plugin files

```javascript
"external_scripts" : [
	"<full address of the paho mqtt javascript client>"
],
```

To load the plugins in your instance of freeboard you will have to add them to the list used to initialize freeboard, for example below is a section of the default index.html that I have extended to load the two plugins.

```html
<script type="text/javascript">
	head.js("js/freeboard+plugins.min.js",
			"plugins/thirdparty/ibm.iotfoundation.plugin.js",
			"plugins/thirdparty/paho.mqtt.plugin.js",
			// *** Load more plugins here ***
			function(){
				$(function()
				{ //DOM Ready
					freeboard.initialize(true);
				});
			});
</script>
```