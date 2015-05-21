Notes for study
===============

## CH2: State Management and Drawing Geometric Objects
----

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

#### Basic State Management
void glEnable(GLenum cap);  
void glDisable(GLenum cap);  
GLboolean glIsEnabled(GLenum capability);  
void glGetBooleanv(GLenum pname, GLboolean *params);  
void glGetIntegerv(GLenum pname, GLint *params);  
void glGetFloatv(GLenum pname, GLfloat *params);  
void glGetDoublev(GLenum pname, GLdouble *params);  
void glGetPointerv(GLenum pname, GLvoid **params);  

#### Displaying Points, Lines, and Polygons
void glPointSize(GLfloat size);  
void glLineWidth(GLfloat width);  
void glLineStipple(GLint factor, GLushort pattern);  
void glPolygonMode(GLenum face, GLenum mode);  
> Controls the drawing mode for a polygon's front and
> back faces. The parameter face can be
> GL_FRONT_AND_BACK, GL_FRONT, or GL_BACK; mode can be
> GL_POINT, GL_LINE, or GL_FILL to indicate whether the
> polygon should be drawn as points, outlined, or filled.
> By default, both the front and back faces are drawn
> filled.  

void glFrontFace(GLenum mode);
> Controls how front-facing polygons are determined. By
> default, mode is GL_CCW, which corresponds to a
> counterclockwise orientation of the ordered vertices of
> a projected polygon in window coordinates. If mode is
> GL_CW, faces with a clockwise orientation are
> considered front-facing.

void glCullFace(GLenum mode);  
> Indicates which polygons should be discarded (culled) before
> they're converted to screen coordinates.
> The mode is either GL_FRONT, GL_BACK, or GL_FRONT_AND_BACK to
> indicate front-facing, back-facing, or all polygons.
> To take effect, culling must be enabled using glEnable() with GL_CULL_FACE;
> it can be disabled with glDisable() and the same argument.


void glPolygonStipple(const GLubyte *mask);  
glEnable(GL_POLYGON_STIPPLE);  
glDisable(GL_POLYGON_STIPPLE);  

void glEdgeFlag(GLboolean flag);
void glEdgeFlagv(const GLboolean *flag);
> Indicates whether a vertex should be considered as initializing a boundary
> edge of a polygon. If flag is GL_TRUE, the edge flag is set to TRUE (the
> default), and any vertices created are considered to precede boundary
> edges until this function is called again with flag being GL_FALSE.
