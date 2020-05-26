# TD-Initiative-Library

The TD Initiative Library is a collection of TOXs and Projects for TouchDesigner whose purpose is to ease the creation of networks and showcase useful techniques.

Nodes are made to be used as is, with custom parameters already prepared, but we strongly encourage you to take a look inside and changes them according to your needs.

## Nodes & TOXes

### COMP

**Set OP Color** (tox)

Allow for changing the color of a node simply by dropping it on it while it is active or by clicking on the desired color. The colors can be personalized easily from inside the node.

The bottom row of colors is set to the default colors of Operators in TouchDesigner. This is useful for deeper integration of COMPs whose work is closely related to a specific family of operators. 
Nodes in the library are colored with it.

### CHOP

**Duplicate** (tox)

Takes a CHOP input and duplicate and rename the specified channels with the specified new names. Its purpose is to prevent cluttering of your networks with simple operations. 

**Placeholder** (tox)

Provides default channels when they are missing. 
For example, a Midi In might be missing some channels until you interact with their related buttons, this can cause reference errors down the line. The Placeholder may be used to prevent that, by making sure a channel with the desired name is always present.  

**TapTempo** (tox)

Takes an input pulse to set the project tempo and provides a beat on the calculated tempo that can be rounded at will.
While doing live performance, it is useful to be able to set the project tempo according to the ambient sound. The Tap Tempo input can come from a MIDI/OSC Button, A Keyboard event, etc. The user has complete freedom over the way of interacting with it.

**ChannelController** (tox)

Allows to select specified channels from its inputs, rename them, apply a specified logic behaviour, modify their range and apply lag.
Useful for mapping MIDI, OSC, Serial, etc. channels to a specific behaviour. A user might want to change the behavior of a momentary button on its MIDI Controller to a toggle button

**IndexCounter** (tox)

Takes two CHOP inputs (preferably normalized MIDI events) and use them to increase and decrease the index of a counter that you can set up. Suggested use: can be convenient to navigate through video sources.

**CHOPDisplace** (tox)

Displace a TOP input according to a CHOP input. The given CHOP channel will displace the input using its amplitude.

### DAT

**JSON** (tox)

The JSONToTable DAT takes a JSON input and outputs each values in the JSON with its path in a two-column table.

The TableToJSON DAT takes a two-column path-value table and outputs its JSON representation.

This is useful when receiving JSON Data from an external source such as an API, making its information easy to use. The TableToJSON can then be used to reformat the data to JSON and send it again.

### Filters

**Delay**

Allows you to delay a TOP input. This can be useful to create effect simulating latency or else. The Delay is a very simple effect, and we encourage you to look inside it.

**Dual Tone**

Allows to change the image tint using its luminance. Low luminance values will be assigned a specific color while high luminance values are assigned another one. This works using the HSV values of the TOP, meaning its saturation and values should be left unchanged.

**RGB Delay**

Delays the red, green-blue layers of a TOP input. It is possible to specify the delay between each layer. Changing the delay order is not possible with the custom parameters, but can be done inside the node.  

**Jitter**

Add a jitter effect to the given input TOP. The jitters effect simulates a shaking and duplication of the image according to a noise. It is possible to control on which axis the jittering occurs as well as other parameters on its behaviour.
