# Texture sharing addon V5.0.0 for Blender 3.x upwards

Blender addon that allows to share textures via [Spout](http://spout.zeal.co/) or [Syphon](https://syphon.github.io/) from and to blender.

This works for current Windows and OSX.

⚠️ This library is still *in development*.

## State of Development

- [x] OSX Syphon Metal Server
- [x] OSX Syphon OpenGL Server
- [x] OSX Syphon Server Discovery
- [x] OSX Syphon Metal Client (blender 4.x upwards) 
- [ ] OSX Syphon OpenGL Client

- [x] Windows Spout Sender
- [ ] Windows Spout Server Discovery
- [ ] Windows Spout Receiver

## Installation

Please make sure you have the most current Blender installed.

1. [Download](https://github.com/maybites/blender.script.spout/releases) the addon from the **releases**

2. Open Blender > Menu >  Preferences > Add-ons > search for and enable the 'TextureSharing' add-on  

3. Press the button to install the SpoutGL or syphon-python library via pip.

4. Once the library is installed, disable and reenable the addon.

5. Save and close preferences.

## Usage

See the current limitation above under **State of Development**

### Sharing Textures

For sharing you need a **Camera** object.

The plugin adds a panel to the **Camera** properties called 'Share texture'. The following properties are available:

![Panel](./documentation/panel.png)

* The sender (also known as syphon-server) name is default set to the camera name.
* use color management (recommended).
* vertical flip of the output texture.
* show preview inside viewport.
* capture/streaming resolution.
* chose a workspace with the desired render / shading preferences.
* chose a scene and layer setup to render.

You should be able to create as many **Cameras** and share textures as you wish.

### Receiving Shared Textures

The plugin adds a panel to the UV-Editor Tools 'Share texture'.

![Panel](./documentation/receivePanel.png)

* create a new image and name it accordingly (in the above case 'Syphon')
* press update to get all available shared textures.
* select a sender/server
* press 'create'
* select the image inside the pane.
* enable the receiver

The receiver will automatically adjust the image size to the size of the received texture. 

Caveat: With the current implementation the update speed is very low (a few frames a second). 
Thats because the received texture needs to be copied from the GPU into an image buffer on the CPU.
For the time beeing I dont see another way to solve this.

## Credits

Blender Plugin by Martin Froehlich.

### Special Thanks:

* Lyn Jarvis for developing [Spout](http://spout.zeal.co/)
* Tom Butterworth and Anton Marini for developing [Syphon](https://syphon.github.io/)
* Jason for the python wrappper [SpoutGL for Python](https://github.com/jlai/Python-SpoutGL) 
* Florian Bruggisser for the python wrappper [syphon-python](https://github.com/cansik/syphon-python)
* Without the valuable [hint](https://docs.blender.org/api/master/gpu.html#rendering-the-3d-view-into-a-texture) from Jonas Dichelle I would still dab in darkness...
* [CAD_Sketcher](https://github.com/hlorus/CAD_Sketcher) showed me how to dynamically install the needed libraries. Hurray to Opensource!

### Very Special Thanks

Python support by Florian Bruggisser - without him, the flawless working of spyhon in blender would still be a dream.
