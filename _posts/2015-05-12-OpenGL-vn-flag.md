---
layout: post
title: Draw VN flag in OpenGL
description: "How to Draw VN flag in OpenGL?"
modified: 2015-05-12
tags: [OpenGL, cpp]
---

test

{% highlight cpp %}
#include<GL\glut.h>
#include<stdlib.h>
#include<math.h>

void main(int Argc,char **Argv)
{
	glutInit(&Argc,Argv);
	glutInitDisplayMode(GLUT_SINGLE|GLUT_RGB);
	glutInitWindowSize(640,480);
	glutInitWindowPosition(0,0);
	glutCreateWindow("Test");
	Init();
	glutDisplayFunc(Display);
	glutReshapeFunc(Reshape);
	glutKeyboardFunc(Keyboard);
	glutIdleFunc(MyIdle);
	glutMainLoop();
}
{% endhighlight %}
