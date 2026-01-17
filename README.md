# PCBS

PCB boards designed with KiCad.


https://www.youtube.com/watch?v=Poj4V9u9bMg


## Version numbering

V0.X

Refers to prototypes that have not being produced, soldered and tested. Being v0.0 the first prototype.

V1.0 is the version of the schematic that has been produced and tested.

V1.x are iterations of a working design.

v2.x are versions that changed something substancial.


## Best way to share libraries between projects

So, you have your library in a defined path, and you go to File->Add library.

When doing this, you will see that the library has been added with an absolute path (Preferences -> Manage Footprint libraries).

The steps to take are as follows:

Open the project. Go to "Preferences -> Configure Paths..." and define these three new variables:

| Name                      | Path                          |
|:--------------------------|:------------------------------|
| KICAD_USER_SYMBOL_DIR     | <path_to_library>/symbols     |
| KICAD_USER_FOOTPRINT_DIR  | <path_to_library>/footprints  |
| KICAD_USER_3DMODEL_DIR    | <path_to_library>/3d_models   |

After that, the libraries should be loaded.


### Creating new libraries steps

You can create a new library like "File -> New Library... -> Global". Then, choose the name you like, and save it in `<path_to_library>/symbols/<lib_name>`.

If you previously defined the environmental variables, KICAD will autocomplete the path with ${KICAD_USER_SYMBOL_DIR}/<lib_name>. Go check it out at "Preferences -> Manage Symbol Libraries".

Then, go to the "Footprint Editor". The same procedure as with the symbol libraries apply.

Finally, when importing 3D files, the enviromental variable should also autocomplete with `${KICAD_USER_3DMODEL_DIR}/<3d_file>`.


### Footprint parts: M L normal

When importing footprints, some appear with "M" "L" or normal.

This letters stand for:

* M: Most land protrusion (bigger pads)
* N (or no letter): Nominal land protrusion (normal pads)
* L: Least land protrusion (smaller pads)
