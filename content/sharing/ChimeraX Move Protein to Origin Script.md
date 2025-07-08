Written by ChatGPT 4.5-mini-high
- confirmed working 06/07/2025
``` Python
# move_to_origin.py

  

from chimerax.geometry import Place

from chimerax.atomic import selected_atoms

import numpy as np

  

# Get whatever atoms are currently selected

atoms = selected_atoms(session) # returns an array of Atom objects

if len(atoms) == 0:

session.logger.info("No atoms selected. Please select some atoms and rerun.")

else:

# Group atoms by their parent model so each structure moves independently

models = {}

for a in atoms:

models.setdefault(a.structure, []).append(a)

  

for model, sel_atoms in models.items():

# scene_coord gives a NumPy array of the atom's transformed (global) coordinates

coords = np.array([a.scene_coord for a in sel_atoms])

centroid = coords.mean(axis=0)

  

# Build a Place that translates by –centroid (identity axes, shifted origin)

identity_axes = (

(1.0, 0.0, 0.0),

(0.0, 1.0, 0.0),

(0.0, 0.0, 1.0),

)

shift = (-centroid[0], -centroid[1], -centroid[2])

translation = Place(axes=identity_axes, origin=shift)

  

# Compose with the model’s existing scene_position

new_place = translation * model.scene_position

model.scene_position = new_place

  

session.logger.info(f"Moved model #{model.id} ('{model.name}') to the origin.")
```