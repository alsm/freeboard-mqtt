freeboard-mqtt
==============

MQTT plugin for [freeboard.io](https://freeboard.io)

MQTT 3.1.1 is an ISO standard publish-subscribe based message protocol for fast and secure IoT communication over TCP/IP.

For a quick demo, try the [IBM Watson IoT Quickstart](https://quickstart.internetofthings.ibmcloud.com/iotsensor/). Add this plugin to Freeboard.io by logging in and editing your board, click "Developer Console" and add the following plugin URL to the list of scripts:
https://rawgit.com/benjaminchodroff/freeboard-mqtt/master/clearobject.mqtt.plugin.js

Add a new datasource to your freeboard and select the MQTT plugin. Enter any name for this plugin, substitute the DEVICEID shown in the upper right of the quickstart in the topic setting, and click "Save". In Freeboard, add a pane, and then in your pane click the "+" icon to add a text widget. In the widget, you can click the "+ Datasource" button and enter a value such as datasources["Example"]["16e158b44ac0"]["d"]["temp"] where "Example" is the name of your datasource and 16e158b44ac0 is the DEVICEID.

Save your widget, and freeboard will show the data returned from your datasource as you update it!

This opensource plugin is community supported with help from [ClearObject](https://www.clearobject.com), [Eclipse Paho](https://www.eclipse.org/paho/), and [IBM Watson IoT](https://internetofthings.ibmcloud.com). Contact [Benjamin Chodroff](mailto:benjamin.chodroff@clearobject.com) for IoT assistance.

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

This plugin uses a cloud hosted version of Paho MQTT Javascript. If you do not have access to the internet, you will need to modify clearobject.mqtt.plugin.js and reference a local version of the Paho MQTT javascript library.

