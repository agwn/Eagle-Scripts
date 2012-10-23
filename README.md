Eagle-Scripts
=============

Collection of Eagle Scripts and Configs


Script: Export Module Footprint
-------------------------------
Procedure
<ol>

<li>
Get eagle files for module
<ol type="a">
<li>Scripts don't seem to run out side of projects. If there is not an eagle.epf file in the directory you will need to create one to "turn it into a project" (empty is ok)</li>
</ol>
</li>
<li>
Add attributes to the components to indicate which ones should be included in the footprint
<ol type="a">
<li>add the attribute 'EXP2MODFP' to all headers that should be "exported to the module footprint"</li>
<li>add the attribute 'EXP2MODMECMNT' to all mechanical mounting points to exported</li>
</ol>
</li>
<li>
Run the script 'run exp-module-fp.ulp' from the open project to create a module\_fp.scr. This script contains all of the eagle commands to generate the exported module footprint in another eagle context. 
</li>
<li>
Import the footprint into a library
<ol type="a">
<li>open a library to import the module footprint into</li>
<li>create a new footprint for the module</li>
<li>source the exported script 'scr module\_fp' or just 'scr' and search for it</li>
<li>cleanup the import to remove things like random text on layers</li>
</ol>
</li>
<li>
If needed create a symbol with the same (or less) pins than were exported for the footprint
</li>
<li>
Create (modify) the library device to include the new footprint
<ol type="a">
<li>open an existing device or create a new device and the symbol for the module</li>
<li>add the footprint to the device, connect the pins and save the library</li>
</ol>
</li>
<li>
Use the new module as a device in a new pcb! :)
</li>
</ol>
