more supercollider, more unity
--------------------

supercollider
--

```
s.boot


```

unity
--

using the webcamera as a texture...

* start unity and create a new project
* select GameObject / 3D Object / Plane
* set the transform scale to  x 5, y 1, z 5 in the plane inspector
* optionally set the transform y rotation to 180 in the plane inspector
* select add component at the bottom of the plane inspector
* select new script and call it something (here 'webcam')

![webcam](01webcam.png?raw=true "webcam")

* doubleclick the script to open it in mono develop
* add the following code...

```javascript
#pragma strict

function Start() {
    var webcamTexture: WebCamTexture = new WebCamTexture();
    var renderer: Renderer = GetComponent.<Renderer>();
    renderer.material.mainTexture = webcamTexture;
    webcamTexture.Play();
}
```

adding more objects to the scene...

* save and go back to unity
* click 'play' and you should see video from your webcamera mapped onto the plane
* add some more objects (here 'sphere')
* drag and drop the webcam script onto the objects in the hierarchy list
* dont forget to position, rotate and scale the objects

![more](02more.png?raw=true "more")

changing the main camera...

* select main camera in the hierarchy list
* click 'play' to go into run mode
* play around with position, rotation and scale in the camera inspector
* picture below show some settings i found fun
* also play around with the projection setting - try with 'orthographic'
* when you're happy remember the settings, click 'stop' and write them into your scene settings

![camera](03camera.png?raw=true "camera")

adding a character...

* select Assets / Import Package / Characters
* just click 'import' in the window that pops up to import everything
* go to 'Project' tab and then expand Assets
* find Standard Assets / Characters / ThirdPersonCharacter / Prefabs / ThirdPersonController
* drag&drop ThirdPersonController onto the plane
* click 'play' and try running around with the arrow keys - space to jump

![tpc](04tpc.png?raw=true "tpc")

connecting the main camera to the character...

* in the hierarchy list, drag and drop the main onto the thirdpersoncontroller
* position the camera with the inspector to sit slightly behind and above the character

![tpccamera](05tpccamera.png?raw=true "tpccamera")

* play around with settings in the inspector window
* try increasing the jump power, decreasing gravity multiplier etc
* also try turning off 'Skinned Mesh Renderer' for EthanBody and EthanGlasses
* change the main camera x rotation to 90 (looking down onto the plane)

![tpcsettings](06tpcsettings.png?raw=true "tpcsettings")

* etc etc. explore

resources
--

more advanced unity tutorials <https://www.youtube.com/user/SpeedTutor/videos>

Eli's supercollider tutorials <https://www.youtube.com/watch?v=yRzsOOiJ_p4&list=PLPYzvS8A_rTaNDweXe6PX4CXSGq4iEWYC>