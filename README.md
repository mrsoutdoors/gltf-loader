# gltf-loader
Three.js GLTFLoader with OrbitControls

THREE.JS FILES
Downloading files from:
https://github.com/mrdoob/three.js/tree/dev/examples/js/ IS DEPRECATED
"When updating older three.js projects, you may get a warning in the browser such as:
"As part of the transition to ES6 Modules, the files in 'examples/js' were deprecated in May 2020 (r117) and will be deleted in December 2020 (r124)."

INSTALLATION is now recommended:
https://threejs.org/docs/index.html#manual/en/introduction/Installation

CALLING THE THREE.JS FILES IN HTML with this method IS DEPRECATED, e.g.
<body>
<script src="three.js"></script>

The IMPORT method should now be used.
https://threejs.org/docs/index.html#manual/en/introduction/Installation
I couldn't use the recommended "install three.js with npm" method due to admin rights on my computer, so I chose the CDN (Content Delivery Network) method.
"Install from CDN or static hosting
The three.js library can be used without any build system, either by uploading files to your own web server or by using an existing CDN.
Because the library relies on ES modules, any script that references it must use type="module"
..."

The Github repository uses CDN (Content Delivery Network) to import the .js files, e.g.
<body>
<script type="module">
import * as THREE from 'https://unpkg.com/three/build/three.module.js';
import { OrbitControls } from 'https://unpkg.com/three/examples/jsm/controls/OrbitControls.js';
import { GLTFLoader } from 'https://unpkg.com/three/examples/jsm/loaders/GLTFLoader.js';

The CDN is the same as is used in this example:
https://jsfiddle.net/8kubjpL5/

HOW TO RUN THINGS LOCALLY
https://threejs.org/docs/index.html#manual/en/introduction/How-to-run-things-locally
"If you load models or textures from external files, due to browsers' same origin policy security restrictions, loading from a file system will fail with a security exception."
The solution: Follow the instructions to "Run a local server" on the above webpage.

Or install XAMPP from: https://www.apachefriends.org/
Place your three.js project folder in the htdocs folder:
C:\xampp\htdocs
Open this file to open the XAMPP Control Panel:
C:\xampp\xampp-control.exe
Start Apache
In your browser's address bar type: localhost/   followed by the name your project folder
E.g. if you have downloaded this tutorial folder from github and have placed it in the htdocs folder,
the URL to type in the browser's address bar would be:
localhost/gltf-loader/

LOADING YOUR OWN MODEL
Replace 'stonehenge.glb' with the file name of your .glb model

CAMERA POSITION
As the stonehenge.glb model is only 46cm high, I adjusted the camera position as follows:

/* Camera */
camera = new THREE.PerspectiveCamera( 45, window.innerWidth / window.innerHeight, 1, 500 );
camera.position.x = 1;
camera.position.y = 1.5;
camera.position.z = 2;
scene.add( camera );

If your model is larger, you may find that the camera is inside your model, so that you can't see it.
Try pasting in the camera settings from the original KMZLoader example:
https://threejs.org/examples/#webgl_loader_kmz
and see how it changes the camera position.
Click the "<> inside the white circle" icon in the bottom right corner of the screen to view the source code.

SKETCHUP MODELS
At the time of writing, SketchUp does not export as .glb/.gltf
SketchUp does export as COLLADA .dae which you can import into Blender, then export as .glb

SOURCE CODE EDITORS
https://notepad-plus-plus.org/	(WINDOWS only)
http://brackets.io/		(MAC and WINDOWS)
