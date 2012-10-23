Eagle-Scripts
=============

Collection of Eagle Scripts and Configs


Script: Export Module Footprint
-------------------------------
Procedure
<ol>

<li>
1. Get eagle files for module
<ol>
<li>a. Scripts don't seem to run out side of projects. If there is not an eagle.epf file in the directory you will need to create one to "turn it into a project" (empty is ok)</li>
</ol>
</li>
<li>
2. Add attributes to the components to indicate which ones should be included in the footprint
<ol>
<li>a. add the attribute 'EXP2MODFP' to all headers that should be "exported to the module footprint"</li>
<li>b. add the attribute 'EXP2MODMECMNT' to all mechanical mounting points to exported</li>
</ol>
</li>
<li>
3. Run the script 'run exp-module-fp.ulp' from the open project to create a module\_fp.scr. This script contains all of the eagle commands to generate the exported module footprint in another eagle context. 
</li>
<li>
4. Import the footprint into a library
<ol>
<li>a. open a library to import the module footprint into</li>
<li>b. create a new footprint for the module</li>
<li>c. source the exported script 'scr module\_fp' or just 'scr' and search for it</li>
<li>d. cleanup the import to remove things like random text on layers</li>
</ol>
</li>
<li>
5. If needed create a symbol with the same (or less) pins than were exported for the footprint
</li>
<li>
6. Create (modify) the library device to include the new footprint
<ol>
<li>a. open an existing device or create a new device and the symbol for the module</li>
<li>b. add the footprint to the device, connect the pins and save the library</li>
</ol>
</li>
<li>
7. use the new module as a device in a new pcb! :)
</li>
</ol>
