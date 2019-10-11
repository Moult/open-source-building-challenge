# open-source-building-challenge

_Note: first draft - please edit!_

This is round one. The objective is simple: **design and document a typical
double storey house using OpenBIM standards and a fully open-source pipeline**.

## The client brief

A double storey house with typical wooden frame construction will be designed
and documented on an imaginary flat site. Documentation shall be produced to a
typical commercial standard for council approval, as well as construction
certification (full detailing of all junctions are required, with scheduling of
all elements).

The exact deliverables are:

 1. A full 3D BIM model of the building in Metric units
 2. A standard set of drawings including cover sheet, plans, sections,
    elevations, perspectives, site plan, shadow analysis, area schedules,
    finishes and materials palette, for a typical council approval.
 3. A standard set of construction drawings including cover sheet, plans,
    sections, elevations, construction details in both 2D and 3D form for all
    junctions, wall types, door jambs, etc and schedules for doors, windows, and
    fixtures.
 4. Sexy marketing 3D renders.
 5. Sexy marketing 3D flythrough animation.

Optional additional deliverables are:

 1. Lighting analysis
 2. Structural analysis
 3. COBie asset management spreadsheet extracted from the IFC file
 4. Construction sequencing
 5. BIM unit tests

In the process of doing this, the objective is to:

 1. Improve open-source BIM software.
 2. Improve OpenBIM content libraries.
 3. Foster online and transparent collaboration in the built environment.

## The rules

The rules of the game are:

 1. There will be at least 4 active collaborators, who will collaborate online.
 2. Git will be used, hosted on Github, as the Common Data Environment (CDE), to
    share, collaborate, and assign tasks (via issues).
 3. One player will act as the client and project manager, who will assign tasks
    and approve designs.
 4. _Only_ open-source software can be used to author the BIM model. Both
    FreeCAD and BlenderBIM must be _equally_ used to author the building, say
    split by top floor and bottom floor. This gives a chance to improve BIM
    capabilities in both programs. No Autodesk, no Graphisoft, no Rhino, no
    SketchUp.
 5. The IFC4 (no IFC2X3) format _must_ be used to exchange all model data. No
    other formats are allowed.
 6. The native models in BlenderBIM and FreeCAD are _not_ allowed to contain
    more information than the IFC model itself (with the one exception of
    parametric geometry). All source of truth data must lie in the IFC file.
    This includes all scheduled data, such as door information, fire ratings,
    acoustic ratings, materials, product brochures, etc.
 7. All documentation, including annotation and schedules, must derive from the
    IFC file. No drawing entire details in pure 2D that are disconnected
    (embedded IFC 2D is fine). No disconnected Excel tables for schedules. Even
    the 3D render must contained referenced materials from the IFC file (e.g. in
    the externally defined surface style entity). Therefore, annotation must be
    smart annotation.
 8. Where the design contains non-project specific elements (e.g. furniture,
    sanitary fixtures, standard steel members), it must be created as an IFC
    content library part which can be reused in future projects, and published
    as part of the OpeningDesign repository free for the world to use.
 9. The building must be structurally viable as verified by a structural
    engineer (can this be done with pure FOSS solutions, or should we make an
    exception?) and have MEP elements modeled (air conditioning, lighting and
    GPOs, plumbing fixtures).
 10. Even though two authoring programs are used, they must federate to author
     the same IFC data. No duplicate of IFC data is allowed (e.g. two IFC files
     with two different GlobalIds referring to the same element). IFC data must
     be able to be referenced or merged. From looking at the IFC file, nobody
     should know it was authored by two programs apart from the Owner History
     entities.

## The players

 1. The project manager / client
 2. Architect / modeler for ground floor using either FreeCAD or BlenderBIM
 3. Architect / modeler for level 1 using the other program
 4. Structural / services consultant
