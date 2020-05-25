# TD-Initiative-Library

## Nodes & TOXes

### COMP

**Set OP Color** (tox)

	Allow for changing the color of a node simply by dropping it on it while it is active. The colors can be personalized easily from inside the node.


### CHOP

**Duplicate** (tox)

	Takes an CHOP input and duplicate and rename the specified channels with the specified new names.

**Placeholder** (tox)

	Provides default channels when they are missing.

**TapTempo** (tox)

	Takes an input pulse to set the project tempo and provides a beat on the calculated tempo that can be rounded at will.

**ChannelController** (tox)

	Allows to select specified channels from its inputs, rename them, apply a specified logic behaviour, modify their range and apply lag.

**IndexCounter** (tox)

	Takes two CHOP inputs (preferably normalized MIDI events) and use them to increment and decrement the index of a counter that you can set up. Suggested use : can be convenient to navigate through sources.

**CHOPDisplace** (tox)

	Displace a TOP input according to a CHOP input.


### DAT

**JSON** (tox)

	The JSONToTable DAT takes a JSON input and outputs each values in the json with its path in a two-column table.

	The TableToJSON DAT takes a two-column path-value table and outputs its JSON representation.

### Filters

**Delay**

	Allows you to delay a TOP input.

**Dual tone**

	Allows to change the image tint using its luminance.

**RGB delay**

	Delays the red, green blue layers of a TOP input.
	
**Jitter**

	Add a Jitter effect to the given input TOP.
