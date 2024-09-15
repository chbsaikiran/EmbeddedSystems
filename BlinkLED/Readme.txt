sudo apt update
sudo apt install python3-pip
sudo pip3 install RPi.GPIO

Code to blinking LED
#######################################################################################################
import RPi.GPIO as GPIO    # Import Raspberry Pi GPIO library
from time import sleep     # Import the sleep function from the time module

GPIO.setwarnings(False)    # Ignore warning for now
GPIO.setmode(GPIO.BOARD)   # Use physical pin numbering
GPIO.setup(8, GPIO.OUT, initial=GPIO.LOW)   # Set pin 8 to be an output pin and set initial value to low (off)
while True: # Run forever
    GPIO.output(8, GPIO.HIGH) # Turn on
    sleep(1)                  # Sleep for 1 second
    GPIO.output(8, GPIO.LOW)  # Turn off
    sleep(1)                  # Sleep for 1 second

########################################################################################################

I connected +ve side red LED to three parallel 330ohms resistors, the other end of resistors is connected to GPIO pin(on Raspberry Pi 3 it is pin 8).

The -ve side of red LED is connected to GND(which is pin 6 on Raspberry Pi 3).