# LaneyCIS27OpenGLDrone
This is a project for Laney CIS 27 Drone project By group 3.<br/>
The group members is currently FUFEI Only, Since my group memeber think it is too hard to handle matrix, projection related things...Please add your name here if you have contribution<br/>
This project is mainly based on this <a href="https://learnopengl.com/">tutorial</a>.Please make sure you had completed these sections:<br/>
<a href="https://learnopengl.com/Introduction">Introduction</a><br/>
<a href=https://learnopengl.com/Getting-started/OpenGL>Getting started</a><br/>
<a href="https://learnopengl.com/Model-Loading/Assimp">Model</a><br/>
<a href="https://learnopengl.com/Advanced-OpenGL/Cubemaps">skybox</a><br/>
Many classes such as,Camera/Shader are based on <a href="https://learnopengl.com/code_viewer_gh.php?code=src/4.advanced_opengl/6.2.cubemaps_environment_mapping/cubemaps_environment_mapping.cpp">this</a> section.

# How to Use
There are 6 libs/header files need to be installed.<br/>
<ol start=1>
<li>OpenGL lib</li>

<li>glfw</li>
<li>assimp</li>
<li>glm</li>
<li>glad</li>
<li>stb_image</li>
</ol>

## Install libs/headers

For Mac user,you are assumed to use <b>Xcode</b>:<br/>
Double click the Drone_Mac.xcodeproj to open it.
<ul>
<li>OpenGL lib:
<ol start=1>
<li>At top left, click <b>the blue project icon </b>with the name Drone_Mac,not the yellow folder.(if the blue project icon doesn't show, click the folder icon under the top left x(exit icon))</li>
<li>click the <b>Build Phases</b></li>
<li>click the <b>Link Binary With Libraries</b>(<a href="https://stackoverflow.com/questions/23177550/what-does-it-mean-to-link-against-something">What does link means</a>)</li>
<li>click the <b>+</b> sign</li>
<li>Search  <b>OpenGL</b></li>
<li>Select <b>OpenGL framework</b>,click Add</li>
<li>Check: Does the <b>Frameworks folder icon</b> in the left column shows that suitcase icon OpenGL.framework?</li>
</ol> </li>

<li>glfw lib: <a herf="https://learnopengl.com/Getting-started/Creating-a-window"> Raw Reference</a>
<ol start=1>
<li><a href="https://brew.sh/">Install Brew</a></li>
<li>Open your terminal(use your paw to scratch the touch pad then go to the <b>other folder</b> if you can not find the terminal)</li>
<li>In your terminal, type "<b>brew install glfw</b>" without quot</li>
<li>Repeat the 1-4 steps in the <b>previous</b> section</li>
<li> this time select <b>Add other..</b></li>
<li>press <b>SHIFT COMMAND G</b> together on your keyboard</li>
<li>type <b>/usr/local/Cellar/glfw/</b>(<a href="https://askubuntu.com/questions/130186/what-is-the-rationale-for-the-usr-directory">what does /usr/ means?</a>) in the prompt, click the <b> x.x.x </b>folder(x is a number) then the <b>lib</b> folder select <b>libglfw.x.x.dylib</b></li> click open
<li>Not finsh yet</li>
<li>repeat <b>1</b> in the <b>previous</b> section</li>
<li>select <b>Build Settings</b> ->search for <b>Header search path</b>. <a href="https://www.quora.com/What-is-the-difference-between-a-header-file-and-a-library-in-c-programming-language">why should I do this?</a></li>
<li>Double click the <b>Header Search Paths</b> 's content(not the title) which is empty now </li>
<li>click the '<b>+</b>' in the prompt, fill with <b>/usr/local/Cellar/glfw/3.2.1/include</b></li>(the number may be different, please check on your own mechine)
</ol>
</li>

<li>assimp
<ol start=1>
<li>It is the same as install glfw. Repeat 2-12 in the previous section but replace the <b>glfw</b> with <b>assimp</b>. There is also difference in the path: the number. <br/>
For example: At step 7: <b>/usr/local/Cellar/glfw/</b> will be <b>/usr/local/Cellar/assimp/</b> <br/>
At step 12: <b>/usr/local/Cellar/glfw/3.2.1/include</b> will be <b>/usr/local/Cellar/assimp/4.1.0/include</b>
</li>
</ol>
</li>
<li>glm
<ol start=1>
<li>glm is different, it don't have a library file, so you only need a  header file</li>
<li>repeat 2-3 and 9-12 in glfw section. Make sure to replace the <b>glfw</b> with <b>glm</b></br>
</ol>
</li>
<li>glad
<ol start=1>
<li>go to this <a href="http://glad.dav1d.de/">website</a> </li>
<li><b>In order</b>,select Language: <b>C/C++</b>, Specification:<b>OpenGL</b>, API/gl: <b>the biggest one</b>, profile:<b>Core</b>, then click generate at the bottom.</li>
<li>Click the zip file shown.A few second later, unzip the folder you download,replace the <b>glad.c</b> file in the xcode project with your <b>src/glad.c</b> file(right click the glad.c file in the xcode, then <b>delete</b>-><b>move to trash</b>, then right click, <b>add file to..</b>, select your glad.c file)</li>
<li>Set up the header search path. Repeat 9-12 steps, fill with the path you unzip the file, such as<b> /Users/IDONTWANTTELLYOUMYNAME/Downloads/glad</b></li>(You can put the downloaded file at any place, just make sure your xcode can find them,means setup <b>header search path</b> the path you put the file)
</ol>
</li>
<li>stb_image
<ol start=1>
<li><a href="https://github.com/nothings/stb/blob/master/stb_image.h">check this</a></li>
<li>It is already setup in this project,which is the "<b>stb_image.h</b>" file.</li>
</ol>
</li>
</ul>

## Set up enviroment

<ol start=1>
<li>Go to <b>Product</b>-><b>Scheme</b>-><b>Edit Scheme</b></li>
<li>click <b>run</b>-><b>option</b></li>
<li>check <b>Working directory</b>-><b>Use Customer Directory</b>->select the current directory(where your project exist)</li>
<li>Replace the const string <b>CURRENTFILEPATH</b> in the <b>main.cpp</b> file with the path you selected.</li>

</ol>

# TODO

<ol start=1>
<li>implement Drone class</li>
<li>add auto navagation feature</li>
<li>add walls</li>
<li>add more objects</li>
<li>implement collison detection</li>
<li>implement AI based on monte carlo, collect the information when auto navagate</li>
<li>implement a console show the Infomation when auto navagation</li>
<li>Add sound</li>
</ol>



