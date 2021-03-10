---
layout: page
title: Resources
permalink: /resources
---

## Parsing OBJ Files  
OBJ file format is a simple format to represent 3D objects. Geometry is represented by vertices (V), faces (F), texture coordinates, normals, etc. For our current purposes, we will focus only on parsing vertices and faces as well as handling comments. For a bit more information on OBJ format you can look [here]([https://en.wikipedia.org/wiki/Wavefront_.obj_file](https://en.wikipedia.org/wiki/Wavefront_.obj_file)). 
### Contents of an .obj File  
The format of the given OBJ files will look something like this

```pseudocode
# this is a comment
v 0.615531 0.373073 7.88049e-005
v 0.681131 0.100991 7.88049e-005
v 0.57373 0.345326 7.88049e-005
v 0.649577 0.0641561 7.88049e-005
...
...
...
f 252 211 251
f 253 251 211
f 211 202 253
f 254 253 202 # another comment
...
...
...
```


 - **Comments (#):** notes that we want to ignore
 - **Vertices (v):** represents a vertex in your object
 - **Faces (f):** represents a triangle with 3 vertex indices.  A vertex's index is determined by the order of the vertices(`v`) in the file.


### Parsing 
Our goal is to parse this file into a bunch of triangles. Assume that we represent a Triangle with a group of 3 vertices and that we have a vec3 structure. The following pseudocode shows one way you could go about parsing an OBJ

```pseudocode
Triangle[] LoadOBJ (file) {

    vec3 vertices[]
    Triangle result[]
    string line
    
    while line = get_line(file) //parse lines until end of file
	    if line starts with "v "
		    x = line.parse_next_double() //parse the first 3 doubles as your vertex
		    y = line.parse_next_double() //can use a string stream or split the line
		    z = line.parse_next_double() // 
		    
		    vertices.push( vec3(x,y,z) )
		    //any comments remaining on the line will not be parsed
		    
		else if line starts with "f "
			v0 = line.parse_next_int() //parse our triangle vertex indices
			v1 = line.parse_next_int()
			v2 = line.parse_next_int()

			triangle = Triangle(vertices[v0], vertices[v1], vertices[v2]) // look up vertices and make triangle
			result.push(triangle)
			
		else if line starts with "#"
			continue  // ignore commented lines
			
	return result
}
```
Notice that we are reading from and writing to `vertices` in the same while loop. This is okay because OBJ files list all vertices before faces. Therefore we won't try to read anything that hasn't already been stored. It is important to check that you are parsing your 3 integers or doubles correctly on each line. Note that the code above will not parse all OBJ files out there. OBJ files can include other tags such as texture coordinates(`vt`) and vertex normals(`vn`). For that you would have to do a bit more parsing and storing, but the overall idea is the same.
