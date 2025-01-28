See the [Github](https://github.com/FyDininno/NodeForm) for installation directions.
# Tutorial
![[SphereSquash.gif]]
Today we will be making the animation above in Blender. And I promise, with Node Form it is way easier than it seems!
## Default Node Path
![[default.png]]
Every time you create a new file in Blender with the add-on enabled, you will see a little element in the scene viewer named "Node Form." If you make it your active object by clicking on it, you can navigate to its "Geometry Nodes" panel to see the default setup shown above. 
1. **Library Import Node**:
	- This allows you to import external Python libraries to be called later in the system.
1. **Dictionary Node**
	- Allows you to simplify your equations by defining variables and expressions.
2. **Start Node**
	- The central node. It runs all the transformations to its "right" side while referencing all the dictionary and library nodes to its "left" side.
## Adding a Node
![[adding_nodes.png]]
**Execute Node**:
This allows you to execute a general piece of Python code. Be careful if you are running Blender with elevated permissions, as it will simply execute the code, and ***this may damage your system!***
## Presets
![[choosing_presets.png]]
### The Spherical Preset
![[spherical_transformation.png]]
As you saw, there are two "Spherical" presets. One is the parameterization found more commonly in mathematics. The "Smooth Spherical Preset" is what we have chosen here because it creates a nice animation. Just make sure that "Delayed Coordinate Interpolation" is selected as the animation type.
# Transformation Parameters
![[selecting_animation_type.png]]
If we take a closer look at the transformation node, it has several parameters:
1. **The Name**: This does not effect the function of the node whatsoever.
2. **X,Y,Z**: Given any vertex with coordinates {x,y,z} (lower case), its new x-coordinate, **X**, will be set to a value according to the equation entered in the first slot. 
3. **t,T**: these variables allow you to do custom animations. The **T** variable references the "Run Time" value. **t** starts from 0 and continues until **T**.
4. **Frame Sparseness**: The lower your frame sparseness, the more tightly packed the animation keys and the higher resolution your animation will be.
## Stacking Transformations
![[composite_transformation.png]]
As you can see, we have wired up another transformation succeeding the Spherical Transformation. Once the start button is pressed, the Spherical transformation will be completed. Next, the coordinates of the sphere will be transformed according to our next transformation node in the path.
## Splitting Transformation Paths
![[Split Paths.png]]
We can see here that after the Spherical Transformation, there are two paths that the animation can go down. In fact, both transformations proceed, in order of which one was connected first, so the sphere will be squashed to a circle if both happen. However, because we have inserted two gate nodes, and only one is open, only the bottom half of the sphere will be squashed down to zero.
## Stacking Dictionaries and Libraries
![[stacking_dictionaries.png]]
Stringing together dictionaries is a very important part of simplifying mathematical expressions. Here, you can see various layers of dictionaries, the "right-most" dictionaries referencing ones behind them via a tree-search.
## Importing Files
![[importing_file.png]]
```Python
def identity_function(value):
	return value

def cap(value, max_value):
	return value if value < max_value else max_value
```
Any external python file can be referenced with this method. Just make sure that the functions you call from it have a return value.
## Putting it All Together
![[everything.png]]
This is how it looks all together. I have added the "Select" node and the "Delete" node to clear the scene every time the start button is pressed.
## Things To Watch out For
1. **Syntax**
	- It is a common mistake that I have made to forget a parenthases somewhere, especially in the dictionary definitions. For example, defining "math.sin" to be "sin" vs "sin(" makes a world of a difference. In one situation, you have to call "sin(x)" and the other you have to call "sinx)". Obviously, it is a better idea to not include the parenthases or else you may get parsing errors.
2. **Dictionary References**
	- You cannot reference definitions created earlier in the same dictionary node.
3. **Troubleshooting**
	- The best way to troubleshoot a problem is to start with a working example, then run change one node at a time while pressing the start button in-between to see where the animation breaks.
4. **Infinities in Your Calculations**:
	- Dividing by zero will cause your animation to crash. Be careful, especially with the time variable. If you cannot avoid dividing by zero, you will have to import a file that catches the exception or returns a different value at the discontinuity.
5. **Errors in the Add-on**:
	- There are errors in the add-on, as of now. For example, when the frame sparseness is different between successive transformations, the animation formats the animation keys undesirably, leading to a warped animation frame at the transition between two successive transformation animations.