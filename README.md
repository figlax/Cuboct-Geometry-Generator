# Cuboct-Geometry-Generator
Grasshopper Generators for cuboct lattice geometries

Grasshopper is a free parametric plugin for Rhinoceros. http://www.grasshopper3d.com/

The most current file is Cuboct_ReinforcedNode_Plate. 

This code is able to generate a Rhino mesh of cuboct lattice geometry with variable pitch, strut width, node reinforcement, and arbitrary size (within computational limits). It also provides the option of integrating a top and bottom plate in the model for testing of 3d printed samples. It also offers limited ability to generate BREP geometry of the arrayed lattice without a plate. 

Using the Code:

1. Download and save the .gh file. Open Rhino and type 'Grasshopper'. Then use the standard dialogue to open the .gh file. You will then see the Grasshopper graphical interface. 
2. On the left hand side is the 'Inputs Section' (blue groups). The ranges of numberical inputs can be changed by accessing the properties of that unit (double click). **MAKE SURE TO USE RHINO FILE UNITS (adjust ranges to fit native rhino file units)**
    - 'Output BREP (no plate)'- offers the ability to output a BREP of the arrayed lattice geometry (with no plating option), but this is not recommended for meshes larger than 5x5x5. Be very carful using this feature! Using it with large lattices will take considerable time and slow your computer (expect 20+ minutes for lattices 10x10x10). Also be sure to turn the toggle switch for this option OFF (False) before closing the file.
    - 'Array Controls'- The number of x, y, and z voxels in your geometry
    - 'Plate?"- True adds a top and bottom plate to the model. False yields arrayed lattice geometry with no plate
    - 'Plate Height'- Controls the height of the top and bottom plate
    - 'Relative Density' (display only)- Displays the relative density of the voxel geometry. Use this  to adjust other geometry when targeting a specific relative density.
    - 'Strut Width'- width of cuboct voxel struts
    - 'Pitch'- lattice pitch
    - 'Height' (Reinforcement Parameter)- this parameter controls the reinforcemnt of the node. A value of zero will yield errors, but theoretically represents no reinforcement of the node. The name height comes from the fact that the controlling parameter is the height that the top plane of the node is 'raised' above the minimum height to increase the size of the node. 
    - 'Node Relative Density' (display only)- This is useful for understanding how much the node has been reinforced relative to the minimum sized node. 
3. On the right most section of the code are the outputs (pink groups). To actually generate the item in Rhino, you will need to 'bake' the component by right clicking and selecting 'Bake'. Note that the first two geometries (labeled BREP) are not available for baking unless the 'Output BREP (no plate)' input value is true. 
4. Once geometry is baked, you will need to clean up and repair the mesh. Use Rhino's 'MeshRepair' function. Unifying normals and fixing naked edges should be expected to be the main problems. Once mesh is cleaned, it is ready for export and printing.
5. Other notes:
   - The middle section of the code contains custom clusters. Double-clicking these will yield a detailed view of the grasshopper code behind them. Meddle with caution. 
   - There is also a section that generates the plain wireframe of the cuboct geometry. 
   - This code currently does not suopport geometry without node reinforcement. 


