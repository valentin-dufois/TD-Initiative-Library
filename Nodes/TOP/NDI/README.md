# NDI Operators

NewTek's NDI® makes it easy to transmit video and audio from one machine to another through the network.

Please refer to this documentation and to the provided exemple in case of any doubt.
In case of any bug, please open an issue about it with a copy of the crash report.

**Warning**
To ensure maximum performances when handling the frames, these custom operators rely on AVX CPU commands. If your CPU dates from after 2012, you should be fine.

Even though any kind of network can support NDI, an Ethernet network with at least a 1 Gb/s bandwidth is strongly recommended.

**Notice**
Although NDI does not specify any limit to the number of video and audio streams, as well as their resolution and other properties, keep in mind that your performances will be limited by your network.

## Custom operators

Please refer to Derivative documentation about how to use custom operators. The DLLs are for windows, the PLUGINs for macOS.

## NDI Out TOP

The `NDI Out TOP` allows you to send a video to any NDI receiver that wants it.
You can send audio alongside the video by specifying a CHOP in the Audio Source.

**Notice** Because NDI is built for audio and video transmission, the sent channels MUST be time sliced. An `Audio File In CHOP` is the perfect type of input. 

**Notice** If this source cannot be found on other computers, please verify you have authorized TouchDesigner to receive UDP and TCP connection on your network. 

### Parameters

- **Active** Enable or disable the source.
- **Source Name** Specifies the name of the source. This source will appear as *yourcomputername (sourcename)* to other NDI receivers.
- **Groups Table DAT** NDI allows every source to be part of one or more groups. The provided `Table DAT` should contain only one column with one group name per row.
- **Audio CHOP** Specifies a `CHOP` whose channels will be sent alongside the video. The channels have to be time sliced.
- **Metadata DAT** Specifies a `Text DAT` whose content will be sent alongside the video. The metadata should be in XML.

### Info CHOP

- **num_connected** Tell how many receivers are connected to this source.

## NDI In TOP

The `NDI In TOP` allows to you to receive video from any NDI source, not only from another TouchDesigner `NDI Out`.
You can see available sources using the `Info DAT` on this node.
The *low bandwidth* setting works both on the frame rate and the resolution of the video, so be sure to check how this parameter affects these values with the `Info CHOP`.

The `NDI In TOP` does not handle audio reception. You have to use the `NDI In CHOP` for this.

### Parameters

- **Active** Enable or disable this receiver.
- **Source Name** The name of the source to connect to.
- **Additional Search IPs** Comma-separated list of additional IPs to scout for NDI sources.
- **Bandwidth** Set the bandwidth to use for receiving the feed. A low bandwidth will adjust the feed resolution and frame rate to reduce network usage.

### Info CHOP

- **connected** Tell if the node is connected to an NDI source.
- **num_sources** Tell how many sources are available

### Info DAT

Provides a list with the name and URI of all the sources found. The sources name are the one you have to enter in the *Source Name* parameter.


## NDI In CHOP

The `NDI In CHOP`

### NDI In TOX

A convenient TOX combining the `NDI In TOP` and `NDI In CHOP` is provided. 
It handles connection of both audio and video nodes, and provides a convenient drop down menu for the source selection in place of an empty string field.

### Parameters

- **Active** Enable or disable this receiver.
- **Source Name** The name of the source to connect to.
- **Additional Search IPs** Comma-separated list of additional IPs to scout for NDI sources.
- **Bandwidth** Set the bandwidth to use for receiving the feed. A low bandwidth doesn't seem to have any effect on the audio.
- **Buffer Size** Set the audio buffer size. The longer the buffer, the higher the delay but less chance of audio artifacts due to bad network.

### Info CHOP

- **connected** Tell if the node is connected to an NDI source.
- **num_sources** Tell how many sources are available

### Info DAT

Provides a list with the name and URI of all the sources found. The sources name are the one you have to enter in the *Source Name* parameter.
