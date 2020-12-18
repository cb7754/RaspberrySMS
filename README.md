# RaspberrySMS
Send and Receive SMS 

I use a modem connected to a raspberry pi 2 B , to receive the status of one system connected too the raspberry. The Raspberry read the sensors and send A SMS with the information whenever the sensor cross a defined threshold, Also I can send commands by SMS to the raspberry to force the reception of the status, to know if the system is running or reboot the raspberry, for instance.
I wrote this code in C but I also create a class in C++ .
The code is very simple  first I setup the modem and send the proper AT commands to setup the SMS.
Then I create thread to receive the SMS and identify the commands. No all phone and send command or ask for info , they must be in a list of authorized number , if not the code rejected them.
Once the SMS command is accepted, you have to create a loop (i.e. while()) to process the command received in the SMS. Yo can add as many commands as you want in the receiving and processCommand functions
