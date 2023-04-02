# Patch: DROID-tuner, version 2
# Author:  @enulun
# 2023-04-01
# Version 2: only uses one P2B8 and Master.
#
# DROID-tuner is a patch for DROID that can help to tune a VCO up to mid octave 6, maybe around E6
# Mordax Data has been used to confirm correct pitches for the DROID patch.
# It works well with sine, triangle and saw.
#
# When/if Der Mann mit der Maschine decides to implement a native
# frequency-counter in the DROID-system, this patch will be obsolete.
#
###################################################################
# QUICK HOW TO USE:
#
# 1. Plug a VCO into I1
# 2. The closest note is shown on button-leds 1-7 (C=1, D=2, etc)
# 3. Press button 8 to show the octave on button-leds 1-7
# 4. Adjust VCO until only 1-2 leds are lit in the Master Panel
#    a) RED colors on the RIGHT: VCO too high, turn it down
#    b) BLUE colors on the LEFT: VCO too low, turn it up
#	   c) 2 WHITE colors on TOP: Perfect tuning (less than 0.01 error)
#
###################################################################
#
# A VCO is connected to I1, and the DROID will show the closest pitch (note), and tuning information
#
# Only one P2B8 controller is needed in addition to the Master.
# The first Pot, and the last button (8) can be pressed for different functions.
# Both the button-leds on the controller, and the Master Panel, are used to give information/feedback
#
# The first Pot is used for changing the speed of pitch detection, between 16s - 0.16s
# Pot position around 0.5 (1.6s) works normally well.
# Lower Pot-values for very low VCO-pitch or for better accuracy, higher to measure pitch faster, but less accuracy.
#
# The buttons 1-7 will light up and show the pitch; 1=C, 2=D, 3=E, 4=F, 5=G, 6=A, 7=B/H
# For black notes 2 buttons will light up, for instance D#/Eb will make both button 2 and 3 to light up.
#
# Pressing button 8 will momentarily change button 1-7 to show which octave the current note belongs to, instead of the note.
# for instance, if the note is "5" (G), and pressing button 8 shows "3", means that the current note is G3.
#
# The Master panel will show the difference in percent between the current VCO-frequency and the nearest pitch we are tuning for.
#
# This difference is visualized with:
#    * BLUE lights on the LEFT side when the VCO-frequency is too low
#    * RED lights on the RIGHT side when the VCO-frequency is too high
#    * TWO WHITE lights on the mid-TOP (-/+0.2% in the figure under), when the VCO-frequency is "perfect"
#
# The lights in the Master Panel symolize the following differences:
#
#  -0.3%  -0.2%  +0.2%  +0.3%
#  -0.5%  -----  -----  +0.5%
#  --------------------------
#  -1.0%  -----  -----  +1.0%
#  -2.0%  -3.0%  +3.0%  +2.0%
#
#  In the figure over, if instead of blue/red leds, both the two mid-top leds (marked +/-0.2%)
#  are lit with WHITE light, it means the difference is less than 0.1%.
#
# So if the current VCO-frequency for instance is 1.2% lower than the nearest note (-1.2%),
# then the 5 left blue lights from -0.1% to -2.0% will light up, and only -3.0% will be off.
# This means that the pitch-difference is better than -2%
# Then, by turning the VCO carefully higher, the blue lights will start to turn off in order.
#
# The same happens with the red lights on the right side if the VCO is higher than the nearest note.
#
# If only one of the lights (red or blue) are lit at the top, it means that the error is between 0.1%-0.2%, which is very good.
# It is said that a human has problem to differ when the error is 0.2-0.35%,
# so two blue/red lights (0.2%-0.3%) should probably often be ok too.
# If the two top leds are lit with withe (less than 0.1%), the difference is near perfection.
#
# It is very hard to make the two mid-top led light white.
# Normally the error will fluctuate a bit, due to inaccuracies in the measurement.
# Then it can help to turn the Pot a bit back, to make it use longer measuring-time.
# For instance, 0.1% error for A4 (440 Hz) will be less than 0.44 Hz, and 0.2% error way less than 1 HZ.
#
# So your quick tuning-goal should be: Turn the VCO until only 1-2 red or blue lights are lit (or white if lucky).
# DONE tuning!
