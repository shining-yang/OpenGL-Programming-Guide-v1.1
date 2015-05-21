Notes for study
===============

## CH2: State Management and Drawing Geometric Objects
====

#### Clearing window
void glClearColor(GLclampf red, GLclampf green, GLclampf blue, GLclampf alpha);  
void glClear(GLbitfield mask);

#### Specify color
glColor*

#### Forcing completion of drawing
void glFlush(void);  
void glFinish(void);

#### Points, Lines, Polygons
void glRect{sifd} (TYPEx1, TYPEy1, TYPEx2, TYPEy2);  
void glRect{sifd}v (TYPE*v1, TYPE*v2);  
void glVertex{234}{sifd}[v] (TYPEcoords);  
void glBegin(GLenum mode);  
void glEnd();  
