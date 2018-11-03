### Incorporating Identity in Art and Technology Education: <br>AR Monuments Workshop
Lead by [Matthew Ganucheau](http://www.ganucheau.com)
<hr>
In this participants will create an AR monument to honor an event in the past or future using open-source web technologies (html,css,js).  Your monument can contain any kind of media you would like to use.  Once placed in a public space you must document and share your monument with the class.       
**Date:** November 3rd 2018  
**Location:** Fort Mason - San Francisco, CA.    
**Event:** [Lenoard 50th Anniversary](https://www.leonardo.info/50th-anniversary)          
**Prerequisites:** None, this workshop will provide support for all levels of expertise. Computers will be provided though laptops are encouraged.  
**Software Used:** HTML, CSS, Javascript, [A-Frame(Web-VR)](https://aframe.io), [AR.js (Web-AR)](https://github.com/jeromeetienne/ar.js)   
**Services Used:** [Neocities](https://neocities.org/)
<br>		
<hr>
<br>
### Part 1: Hello Monument!
1. Head to [Neocities](https://neocities.org/) and creat your account.
2. Open Index.html & replace the existing code with the following:

		<html>
		  <head>
		    <title>Hello Monument</title>
		    <!-- include aframe -->
		    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
		    <!-- include aframe-ar.js -->
		    <script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.6.0/aframe/build/aframe-ar.js"></script>
		  </head>
		  <body>
		  	<!-- enable artoolkit on this scene -->
		    <a-scene embedded artoolkit="sourceType: webcam;">
		    	<!-- define the marker to look for and the object to replace it with  -->
		      <a-marker preset="hiro">
				    <a-sphere position="0 0.5 0" radius="0.5" color="#EF2D5E"></a-sphere>
				    <a-plane position="0 0 0" rotation="-90 0 0" width="2" height="2" color="#7BC8A4"></a-plane>
				  </a-marker>	  
		      <a-entity camera></a-entity>
		    </a-scene>
		  </body>
		</html>

4. Save and View the result.  Your browser will ask for permission to your camera, click Allow.  
5. Test your AR website by placing a [Hiro Marker](https://commons.wikimedia.org/wiki/File:Hiro_marker_ARjs.png) in front of your camera.  Try this on your phone too!
6. Lets see what animation looks like, try replacing the contents of your index.html with the following code:

		<html>
		  <head>
		    <title>Hello Monument</title>
		    <!-- include aframe -->
		    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
		    <!-- include aframe-ar.js -->
		    <script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.6.0/aframe/build/aframe-ar.js"></script>
		  </head>
		  <body>
		  	<!-- enable artoolkit on this scene -->
		    <a-scene embedded artoolkit="sourceType: webcam;">
		    	<!-- define the marker to look for and the object to replace it with  -->
		      <a-marker preset="hiro">
		    		<a-box position='0 0.5 0' material='opacity: 0.5; side: double'>
					    <a-torus-knot radius='0.26' radius-tubular='0.05'>
						    <a-animation attribute="rotation" to="360 0 0" dur="3000" easing='linear' repeat="indefinite"></a-animation>
					    </a-torus-knot>
			    	</a-box>
				  </a-marker>	  
		      <a-entity camera></a-entity>
		    </a-scene>
		  </body>
		</html>

7. Let us view what adding an animated gif textue looks like.  Try Saving the following .gif to your neocities home folder.

		<html>
		  <head>
		    <title>Hello Monument</title>
		    <!-- include aframe -->
		    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
		    <!-- include aframe-ar.js -->
		    <script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.6.0/aframe/build/aframe-ar.js"></script>
		    <!-- include aframe-gif-shader.js -->
		    <script src="https://rawgit.com/mayognaise/aframe-gif-shader/master/dist/aframe-gif-shader.min.js"></script>
		</head>
		<body>
		  	<!-- enable artoolkit on this scene -->
		    <a-scene embedded arjs="sourceType: webcam; debugUIEnabled: false;">
		    	<!-- define the marker to look for and the object to replace it with  -->
		      <a-marker preset="hiro">
		        <a-entity geometry="primitive:box" material="shader:gif;src:url(nyancat.gif);" gif=""></a-entity>
				  </a-marker>	  
		      <a-entity camera></a-entity>
		    </a-scene>
		  </body>
		</html>


8. Next, let's replace the box with a 3D model but first we must find a 3d model. Visit ___ and download a 3d model of your choosing.  Make sure it's under 10 mb and contains two files, an .obj & and and a mtl.  Upload these files to your neocities home directory.
7. Now we can replace our exisiting index.html with the following:

		<html>
		  <head>
		    <title>Hello Monument</title>
		    <!-- include aframe -->
		    <script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
		    <!-- include aframe-ar.js -->
		    <script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.6.0/aframe/build/aframe-ar.js"></script>
		  </head>
		  <body>
		  	<!-- enable artoolkit on this scene -->
		    <a-scene embedded arjs="sourceType: webcam; debugUIEnabled: false;">
		      <!-- load an 3d model and its texture -->
		      <a-assets>
				    <a-asset-item id="obj1" src="myobject.obj"></a-asset-item>
				    <a-asset-item id="mtl1" src="myobject.mtl"></a-asset-item>
				  </a-assets>
		    	<!-- define the marker to look for and the object to replace it with  -->
		      <a-marker preset="hiro">
			      <a-obj-model src="#obj1" mtl="#mtl1" position="0 0 0" rotation="-90 0 0" scale="0.1 0.1 0.1"></a-obj-model>
				  </a-marker>	  
		      <a-entity camera></a-entity>
		    </a-scene>
		  </body>
		</html>


4. Rename mymodel.obj & mymodel.mtl with your correct filenames  
5. Save and View the result

<br>		
<hr>
<br>
### Part 2: Create & Document your sculpture

Pair into groups of 2-3 and create an AR monument to honor an event in the past or future. Begin by having each participant share a topic, location or event they would like to explore.

If you are new to programing tools being used try using an animated gif of your choice to texutre map a box or draw, scan and import to texture map the box.
	
If you are more familure to the programing tools being used try sculpting with a combination of 3D models and A-Frame primitves or modifying an existing 3D model you find. 
	
If you are comofortable to the programing tools being used and who are looking for a challenge try sculpting with a combination of 3D models and A-Frame primitves to create your. 

Once you have completed your scultpltre.  Find a location and document your work in the public space.  Share the documentation, any files used as well as title & description for your group's monument to be shared with the class.

Useful Links:

* [Hexadecimal Colors](https://htmlcolorcodes.com/)
* [A-Frame Documentation – Shapes](https://aframe.io/docs/0.5.0/introduction/html-and-primitives.html)
* [A-Frame Documentation – Animations](https://aframe.io/docs/0.5.0/core/animations.html)
* [How to use other 3D Formats (glTF,DAE,PLY,JSON,FBX) in A-Frame](https://medium.com/@akashkuttappa/using-3d-models-with-ar-js-and-a-frame-84d462efe498)
* [Sculptgl](https://stephaneginier.com/sculptgl/)


Sources for Models:

* [Free3D](https://free3d.com/)
* [NASA 3D Models Collection](https://nasa3d.arc.nasa.gov/models)
* [Turbosquid - Free Section](https://www.turbosquid.com/Search/3D-Models/free)
* [CG Trader - Free Section](https://www.cgtrader.com/free-3d-models)

<br>		
<hr>
<br>

Thank you to to the following brilliant people for paving the way:    
  
* [Elevr.com](http://elevr.com)    
* [Fred Leighton](https://mw18.mwconf.org/paper/the-portarble-museum-developing-augmented-reality-for-the-web-using-ar-js/)   
* [Jerome Etienne](https://aframe.io/blog/arjs/#different-type-of-markers-pattern-and-barcode)
