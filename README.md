# TD-Initiative-Library

## Nodes & TOXes

### COMP

**Set OP Color** (tox)
Allow for changing the color of a node simply by dropping it on it while it is active. The colors can be personalized easily from inside the node.

### CHOP

**Duplicate** (tox)

Takes an input CHOP and duplicate and rename the specified channels with the specified new names

**Midi In** (Custom OP)

Gives MIDI events from a connected MIDI device.

**Placeholder** (tox)

Provides default channels when they are missing.

**TapTempo** (tox)

Takes an input pulse to set the project tempo and provides a beat on the calculated tempo. Suggested use : Use a pulse coming from a MIDI device to set the tempo.

### DAT

**JSON** (tox)

The JSONToTable DAT takes a JSON input and outputs each values in the json with its path in a two-column table.

The TableToJSON DAT takes a two-column path-value table and outputs its JSON representation
