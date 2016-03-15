# Camera

## PROJECT

Camera is a simple C++ 3D camera that you can use in any 3D environment. You can look around using the mouse, and move in all the directions using the keyboard. The calculus is made with simple trigonometry and the project is to be used with OpenGL/glut libraries.

## LICENSE

This project is licensed under the GPL License. See [COPYING](COPYING) for more information.

***

### Install

This project cannot run alone. It just provides a camera class that you can use in your projects. You can check my other project [FFTOcean](https://github.com/CSWest/FFTOcean) if you want to see this camera in action.

***

### Use

The class provides data to *glut*'s library `gluLookAt` function. The computation is made with trigonometric formulas, considering that the viewpoint is at the center of a sphere. The observation point given to `gluLookAt` is one point of that sphere.

To integrate this camera to your project, you need to add a few lines of code in the following *glut* functions:

* `draw()` after `glLoadIdentity()`:
    * `camera.translation();`
    * `gluLookAt(camera.getX(), camera.getY(), camera.getZ(), camera.getSightX(), camera.getSightY(), camera.getSightZ(), 0, 1, 0);`
* `keyboard()`:
    * `camera.setKeyboard(key, true);`
* `keyboardUp()`:
    * `camera.setKeyboard(key, false);`
* `mouseMove()`:
    * `camera.rotation(x, y);`

***

### Gameplay

Using the mouse, you can look around you. You can move using the `Z`, `Q`, `S`, `D` keys as follow:

* `Z`: go forward
* `Q`: translate to the left
* `S`: go backward
* `D`: translate to the right

Please note that the mouse is kept within the window's boundaries, so that you can look all around you (360°). 

***

### Contact

olivier . deiss [at] gmail . com
