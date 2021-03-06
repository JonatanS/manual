# Known Limitations

# Revit

## IDs

Keep in mind that two people using the same Konstru Model in Revit should sync their Revit Models using Worksharing. Otherwise they'll have different IDs in both local Models which might cause confusion.

## Elements

Supported Konstru element types are: Columns, Braces, Beams, Floors, Walls, Grids, Groups, Levels. Analytical elements such as loads are not supported.

## Openings

Symbolic lines in openings might be interpreted as the opening outline. To avoid this either don't use them or make sure they have a line-style \(eg. Thin-Lines\) applied. This way, Konstru can recognize them as annotations.

## Adaptive Components

Adaptive Components will be up- and downloaded by Konstru if family and type are existing in the Revit file. They will be displayed in the web as spheres marking their location points.

## Names

Revit does not support special characters in names for Levels or Grids. The following characters are allowed:  
`A-Z a-z 0-9` and `. _-/'()"`. All Element names are written to the`KonstruName` Text parameter. It should be created automatically - if not, create it manually.

## Custom Profiles

Revit handles profiles in the following order:  
1. Search for types loaded in the document  
2. Search for standard types on the local drive  
3. Create new family and type

# Excel

Excel can only be used to manipulate parameter values, change sections \(by name\) and materials \(by name\). Geometries and IDs can not be modified.

# SAP2000

## Plugin

SAP2000 supports the external plugins. Konstru is developed as plugin and can be reached within SAP2000 models. The external plug-in has to be added manually Tools &gt; Add/ShowPlugins &gt; Add your plug-in. Please see instructions.

## Custom Profiles

Custom sections in regular shapes \(I,C,W,Rectangular etc\) are supported. The irregular shapes currently are not translate via Konstru.

## Grids

Grids are not supported in SAP2000 due to OAPI limitations.

## Levels

There is no model object to represent Konstru levels in SAP. Hence, levels are not supported.

## Openings

Openings are not supported in SAP.

## Analysis Elements

Thermal Load assignments on joint, frame and area not supported.  
Uniform load to frame \(area loads\), Strain loads, surface pressure, temperature, wind pressure loads are not supported.  
Diaphragms are not supported.

## Beams, Braces and Columns

Beams, Braces and Columns are created as frame objects in SAP2000. Label \(is the unique name\) can be overwritten only if the Konstru Name is not duplicated in another frame object.

* Directions : There is no special frame direction, it can be drawn in any way possible. 

## Floor and Walls

Floors and Walls are created as area objects in SAP. The sloped area objects are currently ignored by Konstru but maintained in the model.

# ETABS

## Plugin

Konstru is developed as external plugin for ETABS. The external plug-in has to be added manually Tools &gt; Add/ShowPlugins &gt; Add your plug-in. Please see instructions.

## Custom Profiles

Custom sections in regular shapes \(I,C,W,Rectangular etc\) are supported. Custom profiles can be created via Section Designer during a model download with the Konstru importer. Irregular shapes currently are not translated by Konstru.

## Grids

Grids are not supported in ETABS due to OAPI limitations.

## Levels

Konstru Levels are created as stories in Etabs.

## Analysis Elements

Thermal Load assignments on joint, frame and area not supported  
Uniform load to frame \(area loads\), Strain loads, surface pressure, temperature, wind pressure loads are not supported.  
Diaphragms are not supported.

## Updates

Due to OAPI limitations the area and frame's geometry currently cannot be updated.

## Beam, Column and  Braces

Beams, Braces and Columns are created as frame objects in Etabs. Etabs automatically label the frames as B, D and C depends on the orientation. Vertical frames are columns, horizontal ones are beams and the all others are braces. Unique Name can be overwritten only if the Konstru name is not duplicated in another frame object.

* Directions: ETABS automatically flips the direction of frames \(start and end points\) based on threir end point coordinates: When the member is parallel to the x, y or z axis, ETABS will orien the member suchthat the startpoint has thesmaller X,Y,Z coordinates, and the endpoint has the greater coordinates. The z axis is the governing axis for example when x and y values are negative values. so the lower z value is the start point. similarly if the z value is the same for both ends, the X axis is the governing axis for y values. so the lower x value is the start point.

## Floor and Walls

Floors and Walls are created as area objects in ETABS. The sloped area objects are currently ignored by Konstru but maintained in the model.

# Tekla

## Installation

After installing Konstru for Tekla, if nothing appears after hitting the Konstru toolbar button, a restart of Tekla is required. This is necessary only once.

## Elements

Supported Konstru Elements: Beams, Braces, Columns, Floors, Grids, Levels, Walls.

## Openings

Floor openings are supported, but openings created with shafts from Revit are not. No other openings are supported.

# RAM

## Elements

Supported Konstru Elements: Beams, Braces, Columns, Floors, Grids, Levels, Walls.

## Openings

Floor openings are supported. No other openings are supported.

## Levels

As RAM is very level-driven, it is best to have valid levels present. In cases where valid levels are not present, levels will be automatically created at column endpoints. Framing elements falling within plus or minus 3 feet of a certain level will be created on that level.

