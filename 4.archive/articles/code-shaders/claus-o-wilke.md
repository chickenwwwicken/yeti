Shader programming links and references:

[article](https://clauswilke.com/art/post/shaders)

To the uninitiated, shader programming can appear like magic. 
A few lines of code, written in a C-like language called GLSL, produce enchanting landscapes, fantastic worlds, strange sculptures, or photo-realistic renderings, often animated and rendered in real-time.

### Shadertoy
Can be thought of as the center of the world for the shader programming community.
Allows to write shaders interactively in the browser.

Shadertoy for beginners -> [part 1](https://youtu.be/u5HAYVHsasc)

### Fundamental concepts of 2D rendering
[value noise](https://youtu.be/zXsWftRdsvU)
[voronoi pattern - thCe art of code](https://www.youtube.com/watch?v=l-07BXzNdPw)
[truchet tiling - the art of code](https://www.youtube.com/watch?v=2R7h76GoIJM)
[hexagonal tiling](https://www.youtube.com/watch?v=VmrIDyYiJBA)

### Fundamental concepts of 3D rendering

The core programming technique that is used to render realistic 3D scenes in real time is called ray marching.
It is a relative of ray tracing where we only trace a single ray and apply some other approximations that enable rapid rendering with excellent results. 
The core pieces of a ray marcher are surprisingly simple.

[ray-marching](https://youtu.be/PGtv-dBi2wE)
[soft-shadows](https://youtu.be/2YZClgDWCaM)
[ambient-occlusion](https://youtu.be/2YZClgDWCaM)

### Advanced topics
[Inigo Quilez](https://iquilezles.org/articles/) co-creator of shadertoys and inventor of many tricks now commonly used in ray marching, this link is his website containing useful articles about shader programming and other computer graphics topics.

[presentation](https://iquilezles.org/articles/normalsSDF/) - covers main concepts of ray marching 
[calculating normals](https://iquilezles.org/articles/normalsSDF/)
[generating soft shadows](https://iquilezles.org/articles/rmshadows/)

[live-coding-greek-temple](https://iquilezles.org/articles/rmshadows/)
[live-coding-sphere-gears](https://youtu.be/sl9x19EnKng) - part 1
[live-coding-sphere-gears](https://youtu.be/bdICU2uvOdU) - part 1


### Other
The book of shaders byy paticio gonzalez vivo and jen lowe.

At some point you will probably wanna run your shader outside of the Shadertoy sandbox. 
Learn some basic principles about OpenGL or [WebGL](https://webgl2fundamentals.org/), and how they interact with shaders. 

### Useful code examples
[ray marching starting point](https://www.shadertoy.com/view/WtGXDD)
[integer hash](https://www.shadertoy.com/view/XlXcW4)
[value noise](https://www.shadertoy.com/view/4dS3Wd)
[gradient noise](https://www.shadertoy.com/view/XdXGW8)
[simplex noise](https://www.shadertoy.com/view/Msf3WH)
[wave noise](https://www.shadertoy.com/view/tldSRj)
[efficient soft shadows](https://www.shadertoy.com/view/WdyXRD)
[voronoi - basic](https://www.shadertoy.com/view/MslGD8)
[voronoise](https://www.shadertoy.com/view/Xd23Dh)
[julia set](https://www.shadertoy.com/view/Mss3R8)
[l system](https://www.shadertoy.com/view/XtyGR1)

### Important for www
[making a smiley](https://youtu.be/ZlNnrpM0TRg?feature=shared)
