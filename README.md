# ENGO551 Lab 5

This project is a simple web application that uses MQTT protocol to send and receive messages. It also includes a map view using the Leaflet library.

## Files

- `index.html`: The main HTML file that contains the structure of the web page.

## Usage

1. Go to https://sk-miller.github.io/ in a web browser.
2. Enter the MQTT broker's host and port in the respective fields.
3. Click the `Start` button to connect to the MQTT broker.
4. Click the `End` button to disconnect from the MQTT broker.
5. Click the `Share My Status` button to share your current location and a random temperature value.
6. Enter a topic and message in the respective fields, then click the `Send Message` button to send a custom message.

## Methods

- `onConnect()`: This method is called when the MQTT client successfully connects to the broker. It subscribes to the topic "ENGO551/Shannon/my_temperature".
- `onConnectionLost(responseObject)`: This method is called when the MQTT client loses connection to the broker. If the disconnection was not intentional, it attempts to reconnect.
- `onMessageArrived(message)`: This method is called when a message arrives from the broker. It parses the message, adds a marker to the map at the received coordinates, and binds a popup to the marker displaying the received temperature.
- `start.onclick()`: This method connects to the MQTT broker with the provided host and port.
- `end.onclick()`: This method disconnects from the MQTT broker.
- `share.onclick()`: This method gets the current geolocation, generates a random temperature, and sends this information as a message to the topic "ENGO551/Shannon/my_temperature".
- `send.onclick()`: This method sends a custom message to the entered topic.

## Libraries

- `mqttws31.min.js`: This is the Paho MQTT JavaScript library, which enables the web page to connect to an MQTT broker over WebSocket.
- `leaflet.js`: This is the Leaflet library, which provides interactive maps.

## Note

The application requires a live MQTT broker to function correctly. The geolocation feature requires the user to grant location access. The map view requires an internet connection to load map tiles. The temperature is a random value between -50 and 50.