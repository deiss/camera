# Camera

## PROJECT

Camera is a simple C++ 3D camera that you can use in any 3D environment. You can look around using the mouse, and move in all the directions using the keyboard. The calculus is made with simple trigonometry and the project is to be used with OpenGL/glut libraries.

## LICENSE

Camera - Copyright (C) 2016 -  Olivier Deiss

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received [a copy of the GNU General Public License](COPYING)
along with this program. If not, see <http://www.gnu.org/licenses/>.

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

### Keys

Using the mouse, you can look around you. To move, the keys depend on the keyboard.

##### AZERTY

You can move using the `Z`, `Q`, `S`, `D` keys as follow:

* `Z`: go forward
* `Q`: translate to the left
* `S`: go backward
* `D`: translate to the right

##### QWERTY

You can move using the `W`, `A`, `S`, `D` keys as follow:

* `W`: go forward
* `A`: translate to the left
* `S`: go backward
* `D`: translate to the right 

***

### Contact

olivier . deiss [at] gmail . com
