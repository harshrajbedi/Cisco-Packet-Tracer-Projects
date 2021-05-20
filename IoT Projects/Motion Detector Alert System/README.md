# IoT Project with Motion Detector and Alert System

The purpose of this project is to implement IoT in Cisco Packet Tracer. 

## How this system works
1. Motion Detector on the left side will detect for motion continuously, when it detects motion it's red light will turn on. Now the detector has detected motion.
2. When motion detector senses it send that data to server, in respond our server will do actions based on this data.
3. Server is set to an action whenever motion detector senses anything and that action is to alert the people by turning the bed lamp on.

## Steps for configuring this system
1. To make this system we need 3 devices server, wireless home router, motion detector and a alert device (Lamp).
2. Connect all these devices together by making wired connection from server to home router and then wireless connections to both motion detector and lamp.
3. Assign IP addresses to all 3 devices.
4. Configure Server as Registration server to register motion detector and lamp in the server.
5. Create a rule in the server that if motion detector senses anything then sever will be informed and then it sends data to lamp so that lamp can be turned on.

## Configuring the Registration Server
- Go to Server > Services > IoT > Set Registration Server to on.
- Now Go to Desktop > Enter the IP Address of Server and you will see Registration Server Login
- Click on Sign Up to create a new account and Hit Create.
- Now registration server is configured successfully.

## Registering devices to Registration Server
- Open motion detector and go to Config > Wireless0 > Enter SSID and Password of home router by selecting WPA2-PSK Encryption to connect motion detector with other devices.
- Then Go to Global settings > IoT Server > Select Remote Server > Enter the following Server's IP address, Registration Server's Username and Password and hit Connect.
- Same procedure is to be followed on lamp device.

## Creating Rules in Server
- Go to Server's Desktop and open server's IP address in web browser.
- Sign in with your server's username and password.
- You will see 2 devices with green indicator and on top left click on conditions.
- Click on add button to add actions and create an action such that if sensor is on then server will set lamp status to On and name this action from your choice.
  and then again create a action if sensor is turned of then set lamp status to off. using these 2 actions our lamp will only be turned on if motion detector senses something.
- Now everything is configured successfully, check the working of sensor and alert device by hover your mouse on sensor by keep pressing Alt button from keyboard.
- Now you will see that lamp is turned on when sensor senses mouse movements.
