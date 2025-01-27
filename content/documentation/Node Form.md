# Tutorial

## Default Node Path
![[default.png]]
## Adding a Node
![[adding_nodes.png]]
## Presets
![[choosing_presets.png]]
### The Spherical Preset
![[spherical_transformation.png]]
## Stacking Transformations
![[composite_transformation.png]]
![[selecting_animation_type.png]]
## Special Nodes
![[streamlining.png]]

## Stacking Dictionaries and Libraries


![[stacking_dictionaries.png]]

## Importing Files

![[import_file.png]]
```Python
def identity_function(value):
	return value

def cap(value, max_value):
	return value if value < max_value else max_value

def flor(value, min_value):
	return value if min_value < value else min_value

def barr(value, start_value):
	return 0 if start_value < value else start_value
  
def wall(value, end_value):
	return end_value if value > end_value else 0
```


## Putting it All Together
## Things To Watch out For
### Syntax
### 