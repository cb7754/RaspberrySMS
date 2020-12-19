# RaspberrySMS
Send and Receive SMS 

I use a modem connected to a raspberry pi 2 B , to receive the status of one system connected to the raspberry. The Raspberry read the sensors and send a SMS with the information whenever the sensor cross a defined threshold, Also I can send commands by SMS to the raspberry to do specific action like, force the reception of the status, knows if the system is running or reboot the raspberry.
I wrote this code in C but I also create a class in C++ .
The code is very simple  first: 
  I setup the modem and send the proper AT commands to setup the SMS.
  Then I create thread to receive the SMS and identify the commands. No all phones can send commands or ask for info , they must be in a list of authorized number , if they are     not in the list, the code is rejected the SMS.
  Once the SMS command is accepted, you have to create a loop (i.e. while()) to process the commands received in the SMS. You can add as many commands as you want in the receiving and processCommand functions.
  I used pthread and wiringPi libraries so you have to compile it like this : 
    gcc -o main main.c -lwiringPi -lpthread
