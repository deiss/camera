#### Project: Camera<br/>
#### Author: DEISS Olivier<br/>

This is a simple moving camera that you can use in any C++/OpenGL 3D project.

Language: C++<br/>
Libraries: OpenGL, Glut

-----------------------------------------------------------------------------------

The class provides data to glut gluLookAt() function. The computation is made
with trigonometric formulas, considering that the player is at the center of a
small sphere. The observation point given to gluLookAt belongs to that sphere.

There are only two files in the project, but it cannot work alone. To use it the
right way, you need to call the following:

``` 
	draw():
 		(After glLoadIdentity();)
 		camera.translation();
 		gluLookAt(camera.getX(), camera.getY(), camera.getZ(), camera.getSightX(), camera.getSightY(), camera.getSightZ(), 0, 1, 0);
 
 	keyboard():
		camera.setKeyboard(key, true);
		
 	keyboardUp():
		camera.setKeyboard(key, false);
 
	mouseMove():
		camera.rotation(x, y);
```

-----------------------------------------------------------------------------------

Keys:

You can use the Z, Q, S, D keys and the mouse to move and look all around you.
  - Z: go forward
  - Q: translate to the left
  - S: go backward
  - D: translate to the right
  - Mouse: look

Note that the mouse cannot go out of the window. 



