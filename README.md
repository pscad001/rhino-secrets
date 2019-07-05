# [🦏 Rhino Secrets](https://runxel.github.io/rhino-secrets/)
A collection of cool stuff and lesser known facts on Rhino you might or might not know.

## Rhino

### Symbols in command line
Ever wondered what the specials chars in commands meant? Or are you always forgetting?  

| Char | Meaning |
| --- | --- |
| `*` | Causes the command to repeat automatically without pressing <kbd>Enter</kbd> to restart. (used in macros) |
| `!` | Cancels the previous command. |
| `_` | Runs command as English command name. |
| `-` | Suppress any dialog box. |
| `'` | The apostrophe tells that next command is a nestable command. (geometry creations are never nestable) |
| `/` | If the first character in a toolbar macro is not "!" and the last character is" /", the script runs on the command line without <kbd>Enter</kbd>, so more information can be added. |
| `~` | Suppresses command options for clutter free command feedback. |
| `;` | Comment. (used in macros) |

### Different looking
Take advantage of the possibility to assign a display mode to an object via `_SetObjectDisplayMode`.  
![Artic Viewport with transparent paraboloid](/img/set_obj_display_mode.png"Artic Viewport with transparent paraboloid")

### Fast Osnap
Right-mouse click on an osnap filter in the panel to check that one and uncheck all the others. Right click again to restore the state before.

### Osnaps reloaded
Pressing and holding <kbd>shift</kbd> to reverse the effect of your current Ortho setting.  
Pressing and holding <kbd>alt</kbd> suspends any persistent Osnaps without unchecking them.

### Easy dragging
Long-press LMB on an object to drag and Rhino will find the closest snapping point and use that one while dragging.

### Fast angle snap
Hover your mouse over a point during a command and press <kbd>Tab</kbd> to lock the current angle.

### Elevator mode
When drawing a polyline <kbd>ctrl</kbd> + <kbd>click</kbd> on your previous point to draw vertical regarding the Cplane.

### Elevate during drag
Everybody knows <kbd>shift</kbd> for constraining objects orthogonally on plane; use <kbd>shift + ctrl</kbd> and you can lock it vertically.

### Distance
When prompted for a second point you can also just type in a distance and enter. That constrains the distance from the first point. Then click on something in the correct direction and you're done!

### Select Last
While many operations unselect objects that have just been created or modified, `_SelLast` gives an instant access to them.  
(Mind that the default option `DeselectOthersBeforeSelect` is set to `Yes`. Have you changed it once it should stick.)

### Select specific
`_SelectionFilter` gives you a dockable menu which let you omit whatever geometry types you want from being selected.

### Select in dense areas
When selecting in dense environments, you often want to select around something, but then once clicking to drag your selection window, it already selects something and you end up dragging geometry instead. This can be avoided using the <kbd>alt</kbd> button while making the selection.

### Coordinates
When Rhino prompts for a "next point", typing `.x`, `.y` or `.z` (or even combinations like `.zx`) constrains the following point input to that coordinate. Very useful when selecting points in different viewports.

### Easy Polysurface editing
Give `_SolidPtOn` a try.

### Move on
... with `_MoveUVN`. Works beatifully with `_SelU` and `_SelV`.

### Surfaces want to be one
`_MergeSrf` command to join surfaces together without making a polysurface (makes a new single surface, even if surfaces are not co-planar).  

`_MergeAllFaces` command to turn _coplanar polysurface faces_ into one face.

### Rebuild your edges
If you use the `_RebuildEdges` command it will restore the original trimmed or non-trimmed edges of a surface. This will vastly reduce the amount of newly added control points of most surfaces that are extruded from- or matched to the surface with rebuilt edges.  
You can use this macro with polysurfaces:
```
! _Explode
_RebuildEdges _Enter
_Join
```

### To Infinity...
... and beyond. Use `_IPlane` (alias `ip`) any time you need a plane - to trim with, intersect, Boolean operations, etc. You can even `_FilletSrf` to an IP!

### Gumball galore
Use <kbd>shift + ctrl + left click</kbd> to select the faces or edges of polysurfaces. You can then use the gumball to move/scale/rotate the selection.  

Press <kbd>alt</kbd>, then drag gumball arrow to make a copy.  

<kbd>Shift</kbd> + drag gumball scale box to scale in all directions.  

Scale numerically with a value of `0` in one axis using the Gumball to get the same result as `_SetPt_`.  
Use `-1` for fast mirroring in place.  

<iframe title="vimeo-player" src="https://player.vimeo.com/video/260472052" width="640" height="360" frameborder="0" allowfullscreen></iframe>

### Group-on
<kbd>Ctrl + shift click</kbd> on an object in a group to select that single object without losing the group. 

### They see me rollin'
<kbd>Ctrl + shift + RMB-drag</kbd> rotates the camera around the cursor (when cursor is hover over any geometry).  

When Spinning the view with RMB-drag, press/hold <kbd>shift</kbd> to limit spin to dominant initial rotation axis.

### Perspective is the way to go
With `_OneView` you get dynamic CPlanes.

### View it like it's 1999
Because you want it. `_GradientView`

### What are your favorites?
Find out with `_PopUpPopular`.

### Be a DJ
Use `_Turntable` for some sick beats.

### Dual Monitor
Try `TestMooCow` to synchronize 2 viewports.  
(EXPERIMENTAL)

### Flashing
`TestRandColor`  
(EXPERIMENTAL)

### Sesame Street
Easteregg: `Elmo` is still a valid alias for `_Rebuild`.  
(Why? Because it makes objects soft and friendly...)

### Running Python scripts from aliases or toolbar buttons
[Read on the McNeel forum...](https://discourse.mcneel.com/t/running-python-scripts-from-aliases-or-toolbar-buttons/)

<hr>

## Grasshopper

### What does the red wire do?
You probably already asked yourself what the red wire does in Grasshopper when you accidentally pressed <kbd>Alt</kbd> on your keyboard while wiring components.  
The answer: it names e.g. relays!  
_(Note: at least for me the behaviour is bugged and you need to do this twice, bevor the name gets auto propagated.)_  
![red wiring](/img/red-wiring_1.png)

![red wiring](/img/red-wiring_2.png)
