# FreeCAD shape filler
This FreeCAD Python script takes a given shape (first) and fills this shape with another shape (second).

To read more about FreeCAD programming see [English tutorial](https://www.freecadweb.org/wiki/Python_scripting_tutorial) or [Russian tutorial](https://www.freecadweb.org/wiki/Python_scripting_tutorial/ru).

## Sample code to create a long box shape
```python
import Part
from FreeCAD import Base;

# Create a document with the given name
document = App.newDocument('FreeCAD filler test')

# A box shape
boxShape = Part.makeBox(100, 1000, 100, Base.Vector(0, 0, 0))
# An object to display the shape
box = document.addObject('Part::Feature', 'Box')
box.Shape = boxShape

# Switch to the most convenient view
Gui.SendMsgToActiveView("ViewFit")
Gui.activeDocument().activeView().viewAxonometric()

# Re-draw the document
document.recompute()
```

