# Led_control_with_esp32_wifi
ESP32 Setup:

    Microcontroller:
        The ESP32 is programmed to host a web server that listens for HTTP requests to control an LED connected to one of its GPIO pins.

    Web Server Code:
        The ESP32 code includes routes for handling HTTP requests like /on and /off to turn the LED on and off. Optionally, it hosts a simple web page interface for manual control.

    Wi-Fi Connection:
        The ESP32 connects to a Wi-Fi network and prints its IP address to the serial monitor upon successful connection, enabling communication with the computer.

Computer Setup (Python Script):

    Keyboard Input Detection:
        A Python script listens for specific keyboard inputs (e.g., w for "on" and s for "off") using libraries like keyboard or pynput.

    HTTP Requests:
        The Python script sends HTTP GET requests to the ESP32 web server when specific keys are pressed.

Communication Between Components:

    Detecting Keyboard Input:
        The Python script continuously monitors the keyboard for specific key presses. For example:
            w key to turn the LED on.
            s key to turn the LED off.

    Decision Logic:
        If the w key is pressed, the Python script sends an HTTP GET request to the /on route.
        If the s key is pressed, it sends an HTTP GET request to the /off route.

    Sending HTTP Commands:
        The Python script uses the requests library to send the appropriate HTTP commands (/on or /off) to the ESP32.

LED Control on ESP32:

    Server Handling:
        The ESP32's web server receives the HTTP GET request and calls the corresponding function (handleLedOn or handleLedOff).

    LED Pin Control:
        When the /on route is accessed, the ESP32 sets the GPIO pin to HIGH, turning the LED on.
        When the /off route is accessed, it sets the GPIO pin to LOW, turning the LED off.

    Feedback:
        The ESP32 sends a confirmation response back to the Python script or client (e.g., "LED is ON" or "LED is OFF").


        
