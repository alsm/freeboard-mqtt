freeboard-mqtt
==============

MQTT and IBM IoT Foundation plugins for freeboard.io

To use this plugin with freeboard.io, login and edit your board, click Developer Console, and add the following URL to the list of scripts:
https://rawgit.com/benjaminchodroff/freeboard-mqtt/master/clearobject.mqtt.plugin.js

Alternatively, to use these plugins with your own local copy of freeboard, copy the files into a directory where freeboard will be able to see them, such as plugins/thirdparty in the freeboard main directory. To load the plugins in your local instance of freeboard you will have to add them to the list used to initialize freeboard, for example below is a section of the default freeboard index.html that I have extended to load the plugin.

```html
<script type="text/javascript">
	head.js("js/freeboard+plugins.min.js",
			"plugins/thirdparty/clearobject.mqtt.plugin.js",
			// *** Load more plugins here ***
			function(){
				$(function()
				{ //DOM Ready
					freeboard.initialize(true);
				});
			});
</script>
```

This plugin uses a cloud hosted version of Paho MQTT Javascript. If you do not have access to the internet, you will need to modify clearobject.mqtt.plugin.js and reference a local version of Paho MQTT javascript library.

