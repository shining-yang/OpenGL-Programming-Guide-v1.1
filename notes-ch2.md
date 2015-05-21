## CH2: State Management and Drawing Geometric Objects

#### Clearing window
void glClearColor(GLclampf red, GLclampf green, GLclampf blue, GLclampf alpha);  
void glClear(GLbitfield mask);

#### Specify color
glColor*

#### Forcing completion of drawing
void glFlush(void);  
void glFinish(void);

#### Points, Lines, Polygons
void glRect{sifd}(TYPEx1, TYPEy1, TYPEx2, TYPEy2);  
void glRect{sifd}v(TYPE* v1, TYPE* v2);  
void glVertex{234}{sifd}[v]\(TYPEcoords\);  
void glBegin(GLenum mode);  
void glEnd();  

#### Basic State Management
void glEnable(GLenum cap);  
void glDisable(GLenum cap);  
GLboolean glIsEnabled(GLenum capability);  
void glGetBooleanv(GLenum pname, GLboolean* params);  
void glGetIntegerv(GLenum pname, GLint* params);  
void glGetFloatv(GLenum pname, GLfloat* params);  
void glGetDoublev(GLenum pname, GLdouble* params);  
void glGetPointerv(GLenum pname, GLvoid** params);  

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
> To take effect, culling must be enabled using glEnable() with
> GL_CULL_FACE;
> it can be disabled with glDisable() and the same argument.


void glPolygonStipple(const GLubyte *mask);  
glEnable(GL_POLYGON_STIPPLE);  
glDisable(GL_POLYGON_STIPPLE);  

void glEdgeFlag(GLboolean flag);
void glEdgeFlagv(const GLboolean *flag);
> Indicates whether a vertex should be considered as
> initializing a boundary edge of a polygon.
> If flag is GL_TRUE, the edge flag is set to TRUE (the
> default), and any vertices created are considered to
> precede boundary edges until this function is
> called again with flag being GL_FALSE.

void glNormal3{bsidf}(TYPEnx, TYPEny, TYPEnz);
void glNormal3{bsidf}v(const TYPE *v);
> Sets the current normal vector as specified by the arguments.
> The nonvector version (without the v) takes three arguments,
> which specify an (nx, ny, nz) vector that's taken to be the
> normal. Alternatively, you can use the vector
> version of this function (with the v) and supply a single
> array of three elements to specify the desired normal.
> The b, s, and i versions scale their
> parameter values linearly to the range [-1.0,1.0].

#### Vertex Array
1. Enabling Arrays  
  void glEnableClientState(GLenum array)
> Specifies the array to enable. Symbolic constants
> GL_VERTEX_ARRAY, GL_COLOR_ARRAY, GL_INDEX_ARRAY,
> GL_NORMAL_ARRAY, GL_TEXTURE_COORD_ARRAY, and
> GL_EDGE_FLAG_ARRAY are acceptable parameters.  

  void glDisableClientState(GLenum array);

2. Specifying Data for the Arrays  
void glVertexPointer(GLint size, GLenum type, GLsizei stride,
const GLvoid *pointer);  
void glColorPointer(GLint size, GLenum type, GLsizei stride,
const GLvoid *pointer);  
void glIndexPointer(GLenum type, GLsizei stride, const GLvoid *pointer);  
void glNormalPointer(GLenum type, GLsizei stride,
const GLvoid *pointer);  
void glTexCoordPointer(GLint size, GLenum type, GLsizei stride,
const GLvoid *pointer);  
void glEdgeFlagPointer(GLsizei stride, const GLvoid *pointer);

3. Dereferencing and Rendering  
void glArrayElement(GLint ith);  
void glDrawElements(GLenum mode, GLsizei count, GLenum type,
void *indices);  
void glDrawArrays(GLenum mode, GLint first, GLsizei count);  
void glInterleavedArrays(GLenum format, GLsizei stride, void *pointer);  

#### Attribute Groups
void glPushAttrib(GLbitfield mask);  
void glPopAttrib(void);  
void glPushClientAttrib(GLbitfield mask);  
void glPopClientAttrib(void);  
