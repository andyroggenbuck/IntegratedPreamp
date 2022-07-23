# Integrated Preamp Pedal Clone

I used Altium Designer to design a PCB for a clone of TC Electronic's classic Integrated Preamp guitar pedal. It provides up to 30dB of clean boost, with bass and treble controls.

The circuit is the same as the original TC Electronic pedal except for the power supply, which uses a charge pump to generate a 30V power rail from the standard 9V external DC input. The original pedal required the external supply to provide the operating voltage directly -- the charge pump in this version eliminates the need for a non-standard pedal power supply.

</br>
<p align="center">
  <img alt="Pedal Guts" src="https://github.com/andyroggenbuck/IntegratedPreamp/blob/master/Images/Integrated%20Preamp%20Guts.jpg" width="45%">
&nbsp; &nbsp; &nbsp;
  <img alt="Pedal Exterior" src="https://github.com/andyroggenbuck/IntegratedPreamp/blob/master/Images/Integrated%20Preamp%20Exterior.jpg" width="45%">
</p>
</br>

## Lessons Learned

This was my first design involving a switching power supply, and only my third design using Altium Designer, so I learned a lot. Interesting lessons from this project include:
- Oscilloscope probes pick up radiated EMI! Seems obvious now, but I hadn't encountered it this significantly before.
  - This can be helpful -- hovering the probe over the circuit can show where the noisest parts are. C1, C3, and C5 are connected to the switching pin of the charge pump IC, and they radiate lots of noise.
- Remember the off-board wiring when placing noisy components!
  - I took care to keep the charge pump separated from the audio circuit on the PCB, but the noisiest parts still ended up right next to the signal input jack because I was only thinking about the board layout and not the rest of the assembly.
  - Interestingly, the EMI from the charge pump induces significant 30kHz switching noise in the circuit when the input is unloaded, but it disappears when a signal source is plugged into the input.
- Know where your files are saved!
  - I opened an earlier version of the PCB design from Altium's "local history" and used it as a starting point for a new revision of the layout, and I clicked "Save" without actually knowing where the PCB file was saved. Then Altium crashed, and when I reopened it my file was gone.
  - I needed to save a copy of the PCB file in my project folder and add it to version control. I think the file I worked on was actually in a temp folder.

</br>
<p align="center">
  <img alt="PCB layout" src="https://github.com/andyroggenbuck/IntegratedPreamp/blob/master/Images/PCB%201.jpg" width="32%">
  <img alt="PCB layout top layer" src="https://github.com/andyroggenbuck/IntegratedPreamp/blob/master/Images/PCB%20top%20layer.jpg" width="32%">
  <img alt="PCB layout bottom layer" src="https://github.com/andyroggenbuck/IntegratedPreamp/blob/master/Images/PCB%20bottom%20layer.jpg" width="32%">
  </br>
  </br>
  <img alt="Schematic" src="https://github.com/andyroggenbuck/IntegratedPreamp/blob/master/Images/Integrated%20Preamp%20Sch-1.jpg" width="100%">
</p>
</br>
