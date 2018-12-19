# LabJack_Unipolar_TempController
4-channel unipolar temperature controller with LabJack T7

Schematic, photos and code to run 4 parallel servo loops to control temperature with resistive heating. 

Code optionally publishes error signals and correction voltages on a zmq socket

NOTE: The MOSFETs get hot! Make sure you have a great heat sink. 


Sample usage of python code:



>>> run temp_control.py

Loop running...

Broadcasting on port 5551 with topic temp_control

>>> servo3.turnOn()

Servo on

>>> servo4.turnOn()

Servo on

>>> servo4.gainP(2.5)

Proportional gain updated to 2.50

>>> servo3.gainI(0.07)

Integral gain updated to 0.07

>>> publishOn()

Publishing...

temp_control 1545156654.929000 {'Correction4 (V)': 1.5295926607946055, 'Error1 (C)': 0, 'Error4 (C)': -0.022104144832269412, 'Error2 (C)': 0, 'Error3 (C)': 0.13672319906595476, 'Correction1 (V)': 0, 'Correction3 (V)': 1.5179992313431889, 'Correction2 (V)': 0}

temp_control 1545156657.391000 {'Correction4 (V)': 1.5368803518805427, 'Error1 (C)': 0, 'Error4 (C)': 0.0073884406616002707, 'Error2 (C)': 0, 'Error3 (C)': 0.086090601135310862, 'Correction1 (V)': 0, 'Correction3 (V)': 1.5214884123935588, 'Correction2 (V)': 0}





UPDATE THE CODE WITH THE FOLLOWING:
Lines 18-21: 
The measured resistances of the reference resistors

Lines 31-24: Which LabJack inputs/ouputs correspond to which channels

Lines 37-40: The conversion coefficients to convert your thermistor resistance to temperature

Lines 209-212: Setpoint temperatures
