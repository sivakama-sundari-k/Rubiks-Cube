# Rubiks-Cube
Computer Graphics Mini Project (using OpenGL, C++)
![pic 13](https://user-images.githubusercontent.com/88772143/129011512-58326863-0dc9-41cd-898d-daeea56f69e2.png)
![pic 1](https://user-images.githubusercontent.com/88772143/129011516-4767a1d1-3416-4c3a-b5b9-74ff97d3ab17.png)
![pic 2](https://user-images.githubusercontent.com/88772143/129011517-f4fe091f-884d-4160-a2b1-59744fc616de.jpg)
![pic 3](https://user-images.githubusercontent.com/88772143/129011518-54ff9055-61ac-42ac-9464-ba2eea382576.png)
![pic 4](https://user-images.githubusercontent.com/88772143/129011519-05daa2c3-44a2-453a-b8a8-a656d2066897.png)
![pic 6](https://user-images.githubusercontent.com/88772143/129011520-838649fb-2510-4304-a799-e159996b5954.png)
![pic 7](https://user-images.githubusercontent.com/88772143/129011522-0ee886c4-68b7-44e0-92c1-a807b519b652.png)
![pic 8](https://user-images.githubusercontent.com/88772143/129011525-f71256a9-175b-43a6-988b-431357864ac2.png)
![pic 9](https://user-images.githubusercontent.com/88772143/129011530-f6877107-20d5-4858-9ebb-310c7ad260f6.png)
![pic 10](https://user-images.githubusercontent.com/88772143/129011531-ef769690-ec37-420a-88e2-ca53a4a3508e.png)
![pic 11](https://user-images.githubusercontent.com/88772143/129011532-333356af-097e-4f1e-82e1-011e8f1d3a11.png)
[Understanding the Project.docx](https://github.com/sivakama-sundari/Rubiks-Cube/files/6967536/Understanding.the.Project.docx)

ABSTRACT
The original Rubik’s Cube is a 3D combination puzzle invented in 1974 by Hungarian sculptor and professor of architecture Ernő Rubik and was originally called the “Magic Cube”. This invention caused the widespread interest in the world owing to its unique characteristics, which exerted a profound impact on mankind. Rubik’s Cube is listed as one of the 100 most influential inventions during the 20th century. It consists of 6 faces with each face having the colors red, green, yellow, blue, orange and white. The objective of the game is to make sure all the 6 sides of the cube match the color of the center piece (which cannot be moved). In order to design a RUBIKs Cube having the same concept of the original toy which is to solve the cube to attain the result in which all the 6 sides of the cube match the color of the center piece, we use the concepts of OpenGL programming in which we have implemented our project's ideology. The cube floating in a space can be rotated using either key bind which allow you to rotate a particular piece or with the given user interface which allows you to interact with the cube by the use of the mouse, simply right clicking over the object and choosing the desired option. The speed of rotation of the cube can also be changed, if you wish to increase or decrease the speed by using the respective keys. The shuffled cube can also be solved by pressing the key ‘o’ consecutively until the cube is solved. It is implemented using a simple algorithm. The project has been developed and implemented using C++ and OpenGL in CodeBlocks.

3.4	PSEUDO CODE

3.4.1	   PSEUDO CODE FOR MAIN FUNCTION
•	Step 1: [initialize GLUT]
glutInit(&argc, argy) 
•	Step 2: Set type of buffer and color model. 
•	Step 3: [initialize the window size]
glutInitWindowSize(width,height) 
•	Step 4: [call create window]
glutCreate Window ("Rubik’s Cube") 
•	Step 5: [call init function]
init();
•	Step 6: [call reshape for the current window]
glutReshapeFunc(myreshape);
•	Step 7: [call idle function]
glutIdleFunc(spincube);
•	Step 8: [call mouse function]
glutMouseFunc(mouse);
•	Step 9: [mouse callback function that is to be invoked when the mouse cursor is moved while a button is pressed]
glutMotionFunc(motion);
•	Step 10: [menu with all the keys for movement of the cube is created]
glutCreateMenu(mymenu); 
•	Step 11:[add menu entries]
glutAddMenuEntry(); 
•	Step 12: [attach this menu to right click of mouse]
glutAttachMenu(GLUT_RIGHT_BUTTON); 
•	Step 13: [call keyboard function]
glutKeyFunc(keyboard);
•	Step 14: [call display function]
glutDisplayFunc(display) 
•	Step 15: [call main loop function]
glutMainLoop();

3.4.2	    PSEUDO CODE FOR MYMENU FUNCTION
•	Step 1: [check if rotation complete]
if(rotationcomplete==1)
•	Step 2: [set rotationcomplete=0]
•	Step 3: [switch to “id” and perform corresponding movements]

3.4.3	    PSEUDO CODE FOR KEYBOARD FUNCTION

•	Step 1: [set the variables with values according to the rotation associated with the keybind “key”]
For rotation keys:
rotationcomplete=0;
rotation= (Value of rotation);
inverse = (0 or 1);
solve[++count] = + or – rotation value
glutIdleFunc(spincube);

For rotation about an axis:
Add or subtract the values of p/q/r depending on the axis of rotation.

		 For increasing speed related key:
		 speed=speed+0.3;
		 speedmetercolor[++speedmetercount]=4 or 5;

		 For decreasing speed related key:
		 speed=speed-0.3;
		 speedmetercolor[speedmetercount--]=0;



3.4.4	   PSEUDO CODE FOR MOUSE
•	Step 1: [check for button parameter and state parameter]
When the mouse button is pressed, the x and y coordinates will be set and the resp values will be assigned to variables – beginx and beginy. 
beginx = x;
beginy=y;
•	Step 2: [set “moving” to 1]



3.4.5	  PSEUDO CODE FOR MOTION

•	Step 1: [check if moving == 1]
The beginx and beginy values are reassigned in the mouse function when a mouse button is clicked and the variable moving is set to 1. Therefore, when the mouse is dragged, the cube will be moved as the p and q values are reassigned in this function.
q=q + (x - beginx);
beginx = x;
p=p + (y - beginy);
beginy=y;
•	call glutPostRedisplay();


3.4.6	  PSEUDO CODE FOR SPINCUBE FUNCTION
•	Step 1: [set rotationcomplete=1]
•	Step 2: [based on rotation and inverse rotation, call the functions topc()/rightc()/frontc()/leftc()/bottomc()/backc()]


3.4.7	      PSEUDO CODE FOR TOPC, FRONTC, BACKC, BOTTOMC, RIGHTC,
      LEFTC FUNCTIONS
•	Step 1: [call the transpose() function]
•	Step 2: [place the facets at their right positions]

3.4.8	      PSEUDO CODE FOR TRANSPOSE FUNCTION
•	Step 1: [assign the facets with proper colors according to the rotation]

3.4.9	      PSEUDO CODE FOR DISPLAY FUNCTION
•	Step 1: [clear color and depth buffer bits]
glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
•	Step 2: [load identity matrix]
glLoadIdentity();
•	Step 3: [specify clear values for the color buffers]
glClearColor(0.0,0.0,0.0,0);
•	Step 4: [call speedmeter function]
speedmeter();
•	Step 5: [call output function to display “Rotation Speed”]
output(1,8,message);
•	Step 6: [set color to white]
glColor3f(glColor3f(1,1,1);
•	Step 7: [display the names of members by calling the output function]
output(-9,9,"By:");
output(-9,8,"Saqib Nizam");
output(-9,7,"Vishal Sindhe");
output(-9,6,"Sivakama Sundari");
output(-9,5,"Suriya Jan");
•	Step 8: [display “Right click for controls” using the output function]
output(1,-6,"Right click for controls...");
•	Step 9: [push matrix]
glPushMatrix();
•	Step 10: [rotate the cube so we can see the top, front and the right faces so that we don’t just see the front face]
glRotatef(25.0+p,1.0,0.0,0.0);
glRotatef(-30.0+q,0.0,1.0,0.0);
glRotatef(0.0+r,0.0,0.0,1.0);
•	Step 11: [display the cubies according to the rotation applied]
•	Step 12: [pop matrix]
glPopMatrix();
•	Step 13: [force execution of GL commands] 
 glFlush();
•	Step 14: [perform buffer swap]
glutSwapBuffers();

3.4.10	PSEUDO CODE FOR SPEEDMETER FUNCTION
•	Step 1: [set the color of the triangle of the speedmeter diagram]
glColor3fv(color[7]);
•	Step 2: [draw the triangle]
•	Step 3: [draw the squares of the meter by calling the polygon function]
Repeat for all 15 squares of the meter.
•	Step 4: [draw the final triangle of the meter]

3.4.11	PSEUDO CODE FOR COLORCUBE1, COLORCUBE2, ... , COLORCUBE27     FUNCTION

•	Step 1: [call the polygon() function and pass the color and vertices of the face of the cubie]
      Repeat for all 6 faces.

3.4.12	PSEUDO CODE FOR POLYGON FUNCTION
•	Step 1: [set the width and color of line to black to differentiate between different cubies]
glColor3f(0,0,0);
glLineWidth(3.0);
•	Step 2: [draw the square with bordered by a thick black line]
•	Step 3: [set color of face of cubie]
glColor3fv(color[a]);
•	Step 4: [draw the filled square]
					
3.4.13	PSEUDO CODE FOR OUTPUT FUNCTION
•	Step 1: glRasterPos2f(x,y);
 Used to position pixel and bitmap write operations.
•	Step 2: [count the number of characters and store in a variable]
len = (int) strlen(string);
•	Step 3: [display the string using the respective font]
glutBitmapCharacter (font, string[i]);
