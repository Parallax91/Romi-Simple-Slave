# Romi-Simple-Slave

### Example Usage:

from romi import Romi

robot = Romi() # Instantiate the Romi robot

robot.imu.enable() # Enable the imu, must be done just once

robot.imu.read() # Read the imu data, must be done to get new data (doesn't return data)

gyro_data = robot.imu.g # Get the gyro vector, index the result for x, y, and z data as integers

accel_data = robot.imu.a # Get the accel vector, index the result for x, y, and z data as integers

robot.motors(left, right) # Writes speeds (-300 to 300) to the left and right motors

robot.motor(index, speed) # Writes a speed (-300 to 300) to the indexed motor (0 for left, 1 for right)

encoders = robot.read_encoders() # Reads data from the encoders as a list [left, right]

robot.reset_encoders() # Resets the encoders to zero

robot.play_notes(notes) # Plays a sequence of notes (string formatted after GW Basic, such as "o4l16ceg>c8", see http://pololu.github.io/romi-32u4-arduino-library/class_pololu_buzzer.html#a22f45ef7cdf9dc8fc54e617244368277 for more information)

robot.beepBoop() # Plays the sequence of notes given in the example above

robot.leds(red, yellow, green) # Turns on/off the red, yellow, and green leds (takes three booleans)

buttons = robot.read_buttons() # Reads the states of the 3 buttons (returns a list of three booleans)

batteryMillivolts = robot.read_battery_millivolts()[0] # Reads the current battery voltage, returns a list with an integer value in millivolts
