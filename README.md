# NexaBIM Help

NexaBIM is a suite of productivity tools for Autodesk Revit. It adds a NexaBIM tab to the Revit ribbon with tools for coordinates, element and parameter management, data and 3D export, rooms, modelling, coordination, views and an AI connector for Claude Desktop.

This page is the complete user guide. Press F1 while the pointer is over any NexaBIM ribbon button to open that tool's section of this page directly.

## Contents

* [Requirements](#requirements)
* [Installation](#installation)
* [Uninstalling](#uninstalling)
* [Getting Started](#getting-started)
* [Coordinates](#coordinates)
  * [Location Info](#location-info)
  * [Move to Coordinate](#move-to-coordinate)
  * [Site Coords](#site-coords)
* [BIM Utilities](#bim-utilities)
  * [Copy Studio](#copy-studio)
  * [Element Filter](#element-filter)
  * [Element Tree](#element-tree)
  * [ID Finder](#id-finder)
  * [Standards Transfer](#standards-transfer)
  * [3D Export](#3d-export)
  * [Data Export](#data-export)
  * [Unit Settings](#unit-settings)
  * [Param Ledger](#param-ledger)
  * [Param Sync](#param-sync)
  * [Schedule Manager](#schedule-manager)
  * [Parameter Manager](#parameter-manager)
  * [Link Manager](#link-manager)
  * [Model Clean](#model-clean)
  * [Material Trace](#material-trace)
  * [Level Studio](#level-studio)
  * [Prompt Studio](#prompt-studio)
* [AI](#ai)
  * [NexaAI](#nexaai)
* [Refresh](#refresh)
  * [Refresh View](#refresh-view)
* [Room Tools](#room-tools)
  * [Room Manager](#room-manager)
  * [Boundary Analyzer](#boundary-analyzer)
  * [Room Finish](#room-finish)
  * [Validate](#validate)
  * [Color Code](#color-code)
  * [ElemViz](#elemviz)
* [Modelling](#modelling)
  * [Align](#align)
  * [Snap](#snap)
  * [CAD Import](#cad-import)
* [Coordination](#coordination)
  * [Clash Detection](#clash-detection)
  * [BCF](#bcf)
  * [Nexa Bridge](#nexa-bridge)
  * [Recall](#recall)
* [View Tools](#view-tools)
  * [Organize](#organize)
  * [View Manager](#view-manager)
  * [Section Box](#section-box)
* [Help](#help)
  * [About and Help](#about-and-help)
* [Troubleshooting](#troubleshooting)
* [Frequently Asked Questions](#frequently-asked-questions)
* [Privacy](#privacy)
* [License](#license)
* [Third Party Notices](#third-party-notices)
* [Support](#support)

## Requirements

* Autodesk Revit 2024, 2025, 2026 or 2027.
* Windows 10 or Windows 11, 64 bit.
* A Revit project model for most tools. Tools that need a project tell you when a family document is open.
* Optional: Claude Desktop and your own Claude account, only for [NexaAI](#nexaai). Claude Desktop is a separate product from Anthropic and is not included with NexaBIM. Every other tool works without it.
* Optional: NexaIFC Studio, only for [Nexa Bridge](#nexa-bridge) and the NexaIFC publishing buttons in [BCF](#bcf).
* Optional: a Notion, ClickUp or Trello account, only if you want to send BCF issues as tickets.
* Microsoft Excel is not needed to create workbooks. NexaBIM writes Excel files itself; you only need Excel or another spreadsheet app to open them.

## Installation

1. Get NexaBIM free from the Autodesk App Store and run the installer it provides.
2. Close Revit before installing if it is open.
3. Start Revit. NexaBIM loads automatically and the NexaBIM tab appears on the ribbon.
4. If Revit shows a security prompt for the add in, choose to always load it so the prompt does not return.
5. Open a project model and click any button on the NexaBIM tab.

No account, license key or sign in is needed. The About and Help buttons are also on the Add-Ins tab. NexaAI for Dynamo appears in Dynamo after the first Revit start, and NexaAI is ready to connect from its window once Claude Desktop is installed.

## Uninstalling

1. Close Revit.
2. Uninstall NexaBIM from the Autodesk App Store manager or from Windows Settings, Apps. This removes the program files.
3. Delete the %APPDATA%\NexaBIM and %LOCALAPPDATA%\NexaBIM folders. This also removes the MCP host, NexaAI sessions and logs.
4. If you connected BCF tickets, delete the ticket connections file in %APPDATA%\Nexa.
5. If you used NexaAI for Dynamo, delete the NexaAI for Dynamo folder from each packages folder under %APPDATA%\Dynamo\Dynamo Revit. Until you do, it stays inactive because NexaBIM is no longer loaded.
6. If you used NexaAI, open %APPDATA%\Claude\claude_desktop_config.json, remove the NexaBIM entry under mcpServers, save the file and restart Claude Desktop. The NexaBIM backups next to that file can be deleted too.


## Getting Started

**The ribbon.** Everything lives on the NexaBIM tab, grouped into the panels Coordinates, BIM Utilities, AI, Refresh, Room Tools, Modelling, Coordination, View Tools and Help.

**Split buttons.** Some panel items hold several tools under one button:

* Element Tools holds Copy Studio, Element Filter, Element Tree and ID Finder.
* Param Tools holds Param Ledger, Param Sync, Schedule Manager and Parameter Manager.
* Room Management holds Validate, Color Code and ElemViz.

Click the small arrow under a split button to pick a tool. The button then shows the tool you used last, so one click opens it again.

**Working with tool windows.**

* Most tools open a window that stays open while you keep working in Revit. Clicking the ribbon button again brings the open window to the front.
* A tool window works on the model it was opened from. If you switch to another model, the tool asks you to switch back or to open it again.
* When a tool says Revit is busy, finish or cancel the current Revit command with Escape and try again.
* Nothing in the model changes until you press the tool's apply, create, write or run button. Most changes are made as a single step that Undo in Revit reverses.
* Every control has a short tooltip. Hover over it to see what it does.

**Getting help.** Hover over a NexaBIM ribbon button and press F1 to open its section on this page.

## Coordinates

### Location Info

Read the coordinates of elements, linked elements and picked points in shared, project and internal coordinates, measure between them and export the table to Excel.

**Where to find it:** NexaBIM tab, Coordinates panel, Location Info.

**How to use it:**

1. Select elements in Revit, then open Location Info. The selection is added to the table automatically.
2. To add more, use the source buttons: Selection, Elements, Points, Linked or By Id. For Elements and Linked, pick in the model and click Finish in Revit. For Points, click one point after another and press Escape when done.
3. Choose the frame: Shared for survey coordinates, Project for values relative to the project base point, or Internal for values relative to the internal origin.
4. Choose the unit and the number of decimal places.
5. Select one row to see it in every frame, or several rows to measure them in the inspector.
6. Click Export to write an Excel workbook, or Copy table to put the shown rows on the clipboard.

**Features:**

* Three coordinate frames: Shared, Project and Internal.
* Units in millimetres, metres, decimal feet or feet and inches, with 0 to 6 decimals.
* Latitude and longitude columns when the model has a GIS coordinate system with an EPSG code.
* Choice of the point read on each element: location point, curve start, curve middle, curve end, bounding box center or bounding box bottom center.
* Measuring: one row shows its offsets in every frame, two rows show distance, grid bearing and slope, more rows show size, extents and centroid. Click any value in the inspector to copy it.
* Numbered markers in the active view that follow view changes. Selected rows show in amber.
* Clicking a row selects its element in Revit. Double click or Zoom frames it.
* Coordinates are read again when you return from Revit, and rows of deleted elements are removed.
* Excel export of all rows, shown rows or selected rows, with an optional header of the project, survey point and project base point.
* Settings and Export page for columns, markers, follow mode and export options.

**Tips:**

* Rename a picked point in the inspector so it is easy to recognise in the export.
* In a view without a work plane, picked points snap to faces.
* Feet and inches are written to Excel as decimal feet.

### Move to Coordinate

Move one element so that a source point lands exactly on a destination point.

**Where to find it:** NexaBIM tab, Coordinates panel, Move to Coordinate.

**How to use it:**

1. Select one element in Revit and click Use Selected, or click Pick Element and pick it in the model.
2. Choose the coordinate system for the fields: Shared, Project or Internal, and the display unit.
3. Set the source point with one of the source modes: Element Point for the geometric center of the element, Pick Point on the work plane, or Pick on Element for a point on a face. You can also type the values.
4. Set the destination point by typing coordinates, picking a point, pasting coordinates, or using Use Source, Survey Point or Base Point.
5. Turn on Lock Z if the element should move in plan only.
6. Check the translation shown in the window, then click Move.

**Features:**

* Source modes Element Point, Pick Point, Pick on Element and typed values.
* Destination shortcuts: Use Source, Survey Point position and Project Base Point position.
* Copy and Paste of coordinates between the fields and other programs.
* Live translation and distance display before you move.
* Element status shown before moving: Movable, Pinned, In Group, Not Editable or Hosted.
* A warning before a very large move, for example a destination more than 10 miles from the internal origin.
* Select Moved selects the elements moved in this session.
* Each move is one Revit transaction; Move, Undo, Move gives the same result.

**Tips:**

* Pinned elements must be unpinned first. For an element inside a group, pick the group instead.
* Hosted elements follow their host, so the host may limit the move.
* If shared coordinates are not available in the model, the tool uses Project.

### Site Coords

Set the GIS coordinate system, survey point, project base point, angle to true north and site location of the model in one undoable step.

**Where to find it:** NexaBIM tab, Coordinates panel, Site Coords.

**How to use it:**

1. Open Site Coords and review the Overview page. It shows the current coordinate system, both points in shared coordinates, the angle to true north and the site location.
2. Go to Setup. Under Coordinate system, search by name, EPSG code, country or prefecture, or pick a region, then choose a system. Choose Keep current to leave it unchanged.
3. Under Points, enter the easting, northing and elevation of the survey point and the project base point in shared coordinates.
4. Under True north, enter the angle and choose East or West.
5. Under Location, choose From survey point to compute latitude and longitude through the chosen system, or Manual to type them. Compute from latitude fills the survey point from the latitude and longitude.
6. Review the list of changes in the inspector, then click Apply.

**Features:**

* Built in catalog of EPSG coordinate systems with search, regions, recent picks and a suggested UTM zone for the site.
* Applies the GIS coordinate system without needing a DWG or RVT link.
* Angles in decimal degrees or in degrees, minutes and seconds such as 12 30 15.
* Grid convergence between grid north and true north shown for reference.
* Show points and Hide points switch the survey point, project base point and internal origin in the active view.
* Copy buttons for single values and Copy all for every value as text.
* Import and Export page: JSON files keep everything Setup can apply, Excel writes the model values as numbers in the chosen unit.
* Apply is one Revit transaction named Site Coordinates. Pinned and clipped states are kept and the result is read back and checked.

**Tips:**

* The model geometry does not move. Only the shared coordinates and the survey point marker change.
* Opening a JSON file fills Setup for review. Nothing changes until you click Apply.
* Systems that use US survey feet need the US ft unit when you type their values.

## BIM Utilities

### Copy Studio

Copy elements between open models with Model Transfer, or copy a selection to other levels of the same model with Level Transfer.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Element Tools, Copy Studio. Choose the Model Transfer or Level Transfer tile.

**How to use it, Model Transfer:**

1. Open both models in Revit and make the destination model active.
2. Choose the source model, or click the browse button to open an RVT file as the source.
3. Under Coordinates, choose Shared Coordinates, Project Base Point or Internal Origin to align the models. Compare shows the survey and base points of both models.
4. Choose what to load: everything, what a plan or section shows, what a 3D view shows, or one level only. Click Load Elements.
5. Search, filter by category, parameter values or workset, and check the elements to copy. Revit Selection checks what is selected in the source model.
6. Set the options: group the copied elements into a model group, and choose how duplicate type names are handled.
7. Click Transfer. Afterwards use Log, Show Copied, Isolate and Unisolate to review the result.

**How to use it, Level Transfer:**

1. Add elements with Get Revit Selection, Add Selection, Pick in Model, From Level by category, or Filter, which opens Element Filter.
2. Check the source level. Auto uses the detected level of the elements.
3. Check one or more target levels.
4. Click Copy to Levels. Show Copied selects the last copies.

**Features:**

* Model Transfer copies elements with their hosts, relations and types.
* Smart Copy for rooms, sheets, schedules, spaces, room and space separation lines, levels and grids, each on its own tab with Check All and Copy Selected.
* Duplicate types: keep source types with a suffix, or use destination types.
* Optional model group for the copied elements, with a group name.
* Failure log with element id, category, family, type and reason.
* Level Transfer copies to many levels in one run and reports copied and failed counts per level.

**Tips:**

* If the source file is in use by another Revit session, Model Transfer opens a temporary read copy.
* Levels that already exist in the destination start unchecked in Smart Copy.

### Element Filter

Find elements by category and parameter rules, then select, zoom, isolate, color or section box the results.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Element Tools, Element Filter.

**How to use it:**

1. Pick a category in the Categories list. Turn on In use to show only categories that have elements.
2. Add conditions under Rules. Each condition has a parameter, an operator and a value. Conditions in a group are joined by AND; use Or group to add a group joined by OR.
3. Leave Live on to update the results while you edit, or press F5 to evaluate.
4. Review the results as a List or as a Breakdown grouped by type, family or level.
5. Use the actions on the selected rows, or on every shown row when nothing is selected.

**Features:**

* Text, number and yes or no conditions, including between, with values converted to project units.
* Value suggestions from the model.
* Invert shows the elements that do not match.
* Actions: Select, Zoom, Isolate, Reset, Section box, Color and Export CSV.
* Section box creates a 3D view boxed around the results with an offset in millimetres, and Delete view removes it again.
* Saved and Recent filters, plus filter files you can save and open.
* Auto zoom to the row you pick and a keep on top pin.
* Other tools such as Level Transfer, Element Tree and ElemViz use Element Filter as their advanced filter.

**Tips:**

* Incomplete rules are skipped and counted in the status line.
* Use Ctrl+F to search the results.

### Element Tree

Browse every element of the model in a tree grouped by category, family, type, level or workset, and act on the checked elements.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Element Tools, Element Tree.

**How to use it:**

1. Search the Categories list and click Add to tree, or Add With Filter to add a category filtered by parameter.
2. Choose how to group: category then element, category family type, level then category, or workset then category.
3. Narrow the scope with Level, Created phase and Demolished phase, and search by name or id.
4. Check elements or whole groups.
5. Use the toolbar to act on the checked elements.

**Features:**

* Actions: Select, In View, Zoom, Isolate, Hide, Hide Others, Unhide, Reset, Color by category, Clear Color and Delete.
* Unhide lists hidden elements in the active view so you can pick which ones to show again.
* Category filters: Add Filter, Edit Filter and Clear Filter per category.
* Copy Id or Copy Ids from the context menu.
* Details pane for the selected row.
* Refresh with F5 and delete with the Delete key.

**Tips:**

* Delete removes elements from the model. Use Undo in Revit to bring them back.
* Reset ends the isolation and shows again what this tool hid.

### ID Finder

Find any element by Element Id or Unique Id, or read the id of an element you pick.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Element Tools, ID Finder.

**How to use it:**

1. Type or paste an Element Id or a Unique Id and press Enter or Find. Pasting searches automatically.
2. Or click Pick Element from View. If exactly one element is selected in Revit it is read directly; otherwise you are asked to pick one.
3. Click the result strip to show the full details and actions.

**Features:**

* Detects whether the value is an Element Id or a Unique Id.
* Details: Element Id, Unique Id, category, type, family, level, workset, phase created, design option, owner view and location.
* Copy Id and Copy Guid put the value on the clipboard.
* Zoom, Select, Isolate and Reset View act on the loaded element in the active view.
* Recent lists the elements looked up in this session.
* The pin button keeps the window above Revit.

**Tips:**

* If nothing is found, the element may be in a linked model, in another document, or deleted.

### Standards Transfer

Transfer view templates, view filters, color schemes and materials from another Revit document into the active model.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Standards Transfer.

**How to use it:**

1. Open the target model and make it active.
2. Choose the source document from the open models, or click Browse File to open an RVT or RFA file.
3. Go through the tabs: 3D View Templates, 2D View Templates, View Filters, Color Schemes and Materials.
4. Check the items to transfer. Smart Pick selects everything not already in the active document; Select Missing does the same on the current tab.
5. Click Transfer Selected.

**Features:**

* In Target column that shows which items already exist in the active model.
* Search, Select All and Clear on every tab.
* Items that already exist are kept unchanged and reported.
* Summary of transferred, already present and failed items.

**Tips:**

* The source and target must be different documents.

### 3D Export

Export a 3D view to GLB, glTF, OBJ, FBX and STL with materials, textures and element data.

**Where to find it:** NexaBIM tab, BIM Utilities panel, 3D Export.

**How to use it:**

1. On the Source page, choose the 3D view or click Use active view. Choose the scope: visible in view or selected elements. Choose whether to include linked models, the detail level, and which categories to leave out.
2. On Formats, check one or more formats, choose the output folder and the file name.
3. Adjust Geometry, Materials and Data if needed.
4. Click Analyze to measure the export without writing files.
5. Click Export. Open folder shows the result.

**Features:**

* Formats GLB, glTF, OBJ, FBX and STL in one run.
* FBX writer choice between the NexaBIM writer and the Revit native writer, with embedded textures, up axis, level of detail and edges.
* STL as binary or ASCII, in millimetres or metres, with optional colours.
* Origin: internal origin, project base point, shared coordinates or center at origin.
* Objects per element, by material or merged by material, with a flat hierarchy or by level, by category or by link.
* Mesh options: instancing of repeated geometry, vertex welding, curve quality and double sided faces.
* Materials as Realistic, Shaded or Consistent colors, with exported or embedded textures and a texture size limit.
* Element data with identity or all parameters, optional type parameters and OBJ data files.
* View camera and lights export.
* Analysis of elements, triangles, missing textures and estimated size.
* History page with your recent exports.

**Tips:**

* Run Analyze before exporting a large model.
* Section box, temporary hide and view template settings of the view are respected.

### Data Export

Export sheets, views, schedules and the model to PDF, DWG, DXF, DGN, DWF, IFC, Navisworks, gbXML, images, schedules and SAT in one job.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Data Export.

**How to use it:**

1. On Items, add what to export with Sheets, Views, 3D views, Schedules or Revit selection, then check the items. Search to narrow the list.
2. On Formats, check the formats and adjust the settings of the format in focus, or apply a preset.
3. On Naming and Output, choose the output folder and build the file names from tokens.
4. On Review and Run, read the checks: errors, warnings and notes. Show takes you to the setting behind a check.
5. Click Export. The Results list shows every file and its status.

**Features:**

* Formats: IFC, DWG, DXF, DGN, PDF, DWF, Navisworks, gbXML, Images, Schedules and SAT.
* Built in presets: Drawing set, Combined PDF set, Coordination, Handover and Lossless archive. You can save your own presets.
* Saved selections of items per model, stored on your computer so the model is not changed.
* Token based file names with Project, Number, Model, Name, SheetNumber, SheetName, ViewName, ViewType, Level, Revision, Format, Date and time, plus your own text and a separator.
* Live preview of every file name.
* Existing files: add a number, replace, or skip.
* Optional subfolder per format, a CSV manifest of every file, a zip package, and opening the folder when done.
* Full IFC settings: version, file type, phase, space boundaries, scope, linked models, property sets, classification, IFC class mapping and setups you can load and save as JSON.
* DWG and DXF settings: AutoCAD version, units, coordinates, layer standard, colors, line scaling and export setups saved in the model.
* Preflight checks with Show to jump to the setting.
* History of past exports.

**Tips:**

* The IFC option Store IFC GUID in element parameters writes the IfcGUID to the model after export. Leave it off if the model must not change.
* The output folder is remembered for each model.

### Unit Settings

Set project units for every discipline with Metric or Imperial presets and custom overrides.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Unit Settings.

**How to use it:**

1. Pick a discipline on the left: Common, Structural, HVAC, Electrical, Piping or Energy.
2. Change the unit and the decimal places of any measurement.
3. Or apply a preset: Metric construction, Metric engineering or Imperial architectural, then adjust single rows.
4. The header shows how many changes are pending. Click Apply changes.

**Features:**

* Common: length, area, volume, angle, slope, speed, mass, mass density and time.
* Structural: force, linear force, area force, moment and stress.
* HVAC: temperature, air flow, pressure, velocity, power and power density.
* Electrical: voltage, current, real power, apparent power, frequency, illuminance and luminance.
* Piping: flow, pipe system pressure, fluid temperature and fluid velocity.
* Energy: energy consumption, thermal resistance and heat transfer coefficient.
* All changes are applied together in one transaction.

**Tips:**

* Reload Units discards pending changes and reads the model again.

### Param Ledger

Build a parameter table from the model, filter and sort it, save presets and export to Excel, CSV or JSON.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Param Tools, Param Ledger.

**How to use it:**

1. Pick a category. Every parameter Revit exposes for it is listed.
2. Narrow the list by scope: All Parameters, Instance Only, Type Only or Family Only, and by search.
3. Add columns with Add Selected, Add All, double click, drag, or Smart Columns for a sensible starting set.
4. Edit column headers, reorder them, and mark columns for a sum or a count.
5. Add sort rules and filter conditions joined by And or Or, then click Apply Filter.
6. Choose Excel Workbook, CSV Table or JSON Data, set the output location and click Export.

**Features:**

* Live table preview that always matches the export.
* Blue, green and amber marks for instance, type and family parameters.
* Row options: serial number column, blank line between groups, grouping by the first sort field with subtotals, totals row, element id and unique id columns.
* Schedule title printed above the column headers in Excel.
* Presets that store the category, columns, sort and filters.

**Tips:**

* Sum is available only for numeric parameters.
* Use a preset for any table you export regularly.

### Param Sync

Map and transfer parameter values between elements or between parameters, and import or export values with CSV and Excel.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Param Tools, Param Sync.

**How to use it:**

1. Choose a mode on the left: Element to Element, Parameter to Parameter, Import File or Export File.
2. Set the scope: the Revit selection, a category, the active view or the whole model. For Element to Element, set both source and target and how they are paired: Element ID order, one source to all, or a matching key parameter.
3. For Import File, open a CSV, TXT or XLSX file, choose the sheet, header row and key column with Element ID or Unique ID.
4. Build the mapping rows, or click Auto Match to match parameters by name.
5. Click Preview to see the before and after values. Untick rows you want to skip.
6. Click Apply to write the included rows in one undo step, or Export to save the file in Export File mode.

**Features:**

* Compatibility badges on every mapping row, such as Exact, Convert, Units differ, Parse, Read only and Not found.
* Value transforms per mapping: prefix, suffix, find and replace, letter case, unit conversion, skip empty values and write only into empty targets.
* Preview filter by parameter, Select in Revit, Save preview as CSV and Save Excel report.
* Presets that save the mappings.
* Issue reports saved to Documents, NexaBIM, ParamSync Reports.

**Tips:**

* Run Preview again after changing the mapping; an outdated preview is marked.
* Read only and formula driven parameters are reported, not written.

### Schedule Manager

Export schedules to formatted Excel workbooks with Element Id keys, edit them in Excel and import the values back.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Param Tools, Schedule Manager.

**How to use it:**

1. Tick one or more schedules. Search or filter by category to find them. Double click a schedule to export it at once.
2. Click Export to Excel. Each schedule becomes its own formatted workbook with the row keys on a separate sheet.
3. Edit values on the schedule sheet in Excel and save the file. Sorting and filtering are fine; keep the column headings as they are.
4. Back in Schedule Manager, Browse to the workbook or drop it on the window.
5. Click Preview Changes. Only the cells you changed are listed.
6. Click Apply Changes to write them in one step that Undo reverses.

**Features:**

* Formatted workbooks with a coloured header, alternating rows and fitted column widths.
* Choice of Element Id or Unique Id keys.
* Rows are matched to elements by stable keys, so sorting in Excel does not break the import.
* A list of values that need attention, such as read only parameters, invalid numbers or conflicting values for the same element.

**Tips:**

* Close the workbook in Excel before importing.
* A workbook exported from another Revit document is refused.

### Parameter Manager

Create project, shared and global parameters, manage the shared parameter file, rename parameters without losing values, audit values and edit them in bulk.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Param Tools, Parameter Manager.

**How to use it:**

1. Choose a section in the navigation: Create has Project, Shared and Global; Manage has Rename, Parameters and Shared File; Data has Audit and Bulk Edit.
2. To create a project parameter, enter the name, data type, instance or type binding and group, check the categories and click Create Parameter.
3. To add a shared parameter, open the shared parameter file, pick a parameter and click Add to Project.
4. To rename, pick the parameter, enter the new name and click Rename Parameter.
5. To audit, pick a parameter and click Run Audit.
6. To edit in bulk, load elements, enter new values and click Apply Values.

**Features:**

* Category picker with a Common button for frequent building categories.
* Global parameter creation.
* Parameters list with Copy name, Count elements, Export CSV, Remove from project and category binding edits.
* Shared File editor: new file, open, add, duplicate and delete rows, groups, preview and save.
* Audit with elements, unique values, empty and filled counts, a chart, PNG export, Excel export and copy.
* Bulk Edit with current and new values, Set All on shown rows and selection in Revit.

**Tips:**

* Removing a parameter deletes its stored values. You are asked to confirm first.

### Link Manager

Link RVT, IFC, CAD and point cloud files, manage their status, paths and view visibility, and fix link health issues.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Link Manager.

**How to use it:**

1. The Links page lists every link with its type, status, instances, pinned state, path type, size, date and workset.
2. To add links, click Add Link or drop files on the window, set positioning and options, and click Link File.
3. Select links and use the actions: Reload, Reload From, Unload, Remove, Select instances, Zoom to instances, Pin or Unpin.
4. Open Health to see errors, warnings and healthy links, and click Fix All Safe to pin, make paths relative and reload changed links.
5. Open View Mapping to pair host views with linked views, then click Apply Mapping.

**Features:**

* Supported files: Revit models, IFC, DWG, DXF, DGN, SAT, SKP and point clouds RCP and RCS.
* Positioning: Auto, Shared Coordinates, Origin to Origin, Center to Center, Base Point to Base Point, Base Point to Origin and Survey Point to Origin.
* Options for worksets to open, CAD colors, layers, units and current view only, and what to do when a file is already linked.
* Make Relative, Make Absolute and Copy Path; Overlay or Attachment reference type; Room Bounding on or off.
* Hide or unhide links in the active view.
* All links actions: Reload All, Unload All, Pin All, Unpin All, Remove All and Export Report.
* Status for not found, newer on disk and IFC changed files.
* Move link instances to a workset.
* View Mapping with Add Pair, Match Names, Smart Match by level number and keywords, and CSV export of the pairs.

**Tips:**

* Press F5 to rescan the links.
* Nested links are removed together with their parent.

### Model Clean

Scan, review and delete elements, views, templates and filters, and remove only what is unused with Smart Delete.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Model Clean.

**How to use it:**

1. Choose a section: Categories, Views, Templates, Filters, Parameter Rules, Quick Tools or Smart Delete.
2. Click Scan. Results appear as a checklist grouped by kind.
3. Check what to remove. Use Search, Select All, Clear and Select in Revit to review.
4. Click Review, or Review All Checked to review every section at once.
5. In the review dialog, choose whether to include dependents and whether to unpin and delete pinned items, then delete.
6. Read the results: deleted, kept in use, skipped and failed, each with the reason.

**Features:**

* Templates split into 2D and 3D templates.
* Parameter Rules find elements of a category by parameter conditions.
* Quick Tools: all detail lines, text notes, revision clouds, keynotes, scope boxes, reference planes, room separation lines, imported CAD and orphaned tags.
* Smart Delete: unused families, view templates, filters, materials, groups, schedules, views, color schemes, line styles, filled region types and wall, floor, ceiling and roof types.
* Items in use are protected, such as templates in use, the active or starting view, views on sheets and filters in use.
* Every delete is one undo step.

**Tips:**

* Run Smart Delete again after a large cleanup; removing one item can make others unused.

### Material Trace

Browse every project material with thumbnails and details, see where each one is used, and find unused or duplicate materials.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Material Trace.

**How to use it:**

1. Click Scan Model to find where each material is used.
2. On Library, search and sort the materials, and pick one to see its details and where it is used.
3. Use Select Elements, Isolate Elements or Color Elements for a material.
4. On Inspector, pick an element or follow the Revit selection to see its materials and compound layers.
5. On Health, review unused materials and possible duplicates.
6. On Takeoff, read the quantities per material and export them.

**Features:**

* List and tile views with shading color swatches.
* Detail tabs Overview, Physical and Parameters with graphics, patterns, appearance, texture slots and thermal data.
* Compare two materials and show only the differences.
* Open in Revit opens the material in the Material Browser.
* Health groups possible duplicates by Same Look and Similar Name.
* Takeoff with count, area, painted area and volume for the model or the active view.
* Color View colors the active view by material, with a legend; Reset View removes colors and isolation.
* Export to Excel with takeoff, where used, unused, duplicates and library, or CSV for the takeoff.

**Tips:**

* Colors and isolation applied by the tool are removed on Reset View and when the window closes.

### Level Studio

Write each element's level into the LevelForFilter parameter with Level Filter, then isolate, highlight and check elements by level with Level Focus.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Level Studio. Choose the Level Filter or Level Focus tile.

**How to use it, Level Filter:**

1. Click Create parameter the first time. It creates the LevelForFilter text parameter and binds it to the model categories.
2. Choose the scope: whole model, active view or selection, and optionally a phase and a workset.
3. Check the categories and click Scan.
4. Review the preview. Rows are marked New, Changed, Same or No level.
5. Click Write.

**How to use it, Level Focus:**

1. Choose Active view or Whole model and select one or more levels.
2. Click Isolate, Hide others, Highlight or Select, or New view for a filtered copy of the active view.
3. Click Reset view to clear what Level Focus applied.
4. Click Run check to compare LevelForFilter with the live level parameters. Issues are marked Mismatch, Missing or Unknown.

**Features:**

* Reads the level from Level, Schedule Level, Reference Level, Base Level, Base Constraint and other level parameters, or from the parent for hosted and nested elements.
* Keep existing values so changed values are not overwritten.
* Clear values clears LevelForFilter in scope.
* Export the preview to CSV.
* LevelForFilter can drive view filters, schedules and the Level Focus view copies.

**Tips:**

* Run Level Filter again after major edits so LevelForFilter stays current.

### Prompt Studio

Control the model with plain English prompts, fully offline.

**Where to find it:** NexaBIM tab, BIM Utilities panel, Prompt Studio.

**How to use it:**

1. Type a prompt in the command bar, or pick one from the prompt library.
2. Fill the fields of the prompt, such as category, level, parameter or value, from your model.
3. Click Preview or press Ctrl+P to see how the prompt is understood.
4. Click Run or press Enter.
5. Read the result card. Tables can be copied or saved as CSV and charts are drawn where the prompt asks for them.

**Features:**

* Fully offline. Prompts are understood by pattern matching on your computer with no network access.
* Library tabs Library, Starred, Recent and Mine, with a category filter.
* Prompt groups for selection and visibility, quantities and analysis, quality checks, element editing, multi step workflows, parameters, views, templates, levels, worksets, materials, sheets and schedules, rooms, export, model reports, filters, graphs and project information.
* Examples: Count Walls grouped by level, Select Doors on Level 1, List Rooms without Number.
* Live suggestions while you type and a field composer for prompts with fields.
* Star prompts, save your own prompts with fields, and run again from History.
* Results tab and History tab with copy and clear.

**Tips:**

* If a prompt is not understood, Prompt Studio suggests similar prompts from the library.
* Your starred prompts, history and own prompts are kept in %APPDATA%\NexaBIM.

## AI

### NexaAI

Connect Claude Desktop to Revit and Dynamo through a local connector, follow every request live, review Dynamo code and build Dynamo graphs.

**Where to find it:** NexaBIM tab, AI panel, NexaAI. In Dynamo, Extensions menu, NexaAI.

**How to use it:**

1. Install Claude Desktop and sign in with your own Claude account.
2. In Revit, open NexaAI. On the Connect page, click Connect in the Claude Desktop card. This registers NexaBIM in Claude Desktop.
3. Click Restart Claude so Claude Desktop loads NexaBIM.
4. Check the Revit card. The bridge should show Running.
5. Use Starter prompt to copy a test prompt, then paste it in Claude Desktop.
6. Claude can read the model right away. To let Claude change the model, turn on Model writes and confirm. Model writes are off by default in every Revit session.

**Features:**

* Connect page: Connect or Repair, Restart Claude, Config folder and Install host, plus the Revit bridge with Start, Pause, Start with Revit and Model writes.
* Activity page with request statistics, charts, the most used tools and every operation with its result or error. Running operations can be cancelled.
* Dynamo page: graph status, Python nodes with current and proposed code side by side and changed lines marked, Apply, Run with per node errors and warnings, and installed packages.
* Graph Builder page: graph nodes, node library search, and plans staged by Claude that you can Apply as one undoable step or Reject.
* Tools page: the catalog of tools Claude Desktop sees, with search and descriptions.
* Inspector with live status of the Revit bridge, Claude, Dynamo and model writes.
* The Dynamo extension adds a NexaAI panel in Dynamo with Status, Python, Run and Activity tabs.

**Tips:**

* NexaAI starts with Revit, so Claude Desktop can reach Revit before you open the window. Turn off Start with Revit if you do not want that.
* Pause refuses tool calls until you resume.
* Each change Claude makes can be undone in Revit.
* Applying Dynamo code only writes code. Nothing runs until you press Run.

## Refresh

### Refresh View

Redraw the active view and the other open views to clear stale graphics without changing the model.

**Where to find it:** NexaBIM tab, Refresh panel, Refresh View.

**How to use it:**

1. Click Refresh View.

**Features:**

* Regenerates the model in a step that is rolled back, so the model is not marked as modified and no undo entry is created.
* Repaints the active view and redraws every open view of the model while keeping its zoom and pan.
* Silent when it works. A short message appears only if the view could not be refreshed.

**Tips:**

* Use it when colors or highlights from a tool seem to remain after a reset, or when a view does not repaint.

## Room Tools

### Room Manager

Place, edit, validate, number and visualise rooms with a floor layout and a 3D review.

**Where to find it:** NexaBIM tab, Room Tools panel, Room Manager.

**How to use it:**

1. Rooms shows every room with its name, number, department, level, area and status. Search with Ctrl+F and filter by area, status, level or department.
2. Place runs Place Rooms in closed boundaries; Review Rooms then lists the rooms just placed. Create Room places a single new room.
3. Edit changes the ticked or selected rooms. Set Department, Auto Number and Reset Values help with bulk edits.
4. Review checks duplicates in a column with Check Unique and opens the Room Validator.
5. Analysis opens Room Analysis charts and statistics, or ElemViz.
6. 3D and View switches the viewport between plan and 3D, opens the Room 3D Viewer and shows or hides room fill in the active view.
7. Export writes the visible rows and columns to Excel.

**Features:**

* Model Health with quick filters for no number, duplicate numbers, no name and no department.
* Plan viewport with level switching, color by parameter, room tags, zoom and pan.
* 3D viewport with orbit, pan and standard views.
* Department list and department assignment.
* Delete ticked rooms.
* Keyboard shortcuts for every section and action. Press F1 inside Room Manager for the list.

**Tips:**

* Ctrl+1 to Ctrl+7 switch sections. Enter selects and zooms in Revit.
* Ctrl+D switches between plan and 3D and Ctrl+M expands the viewport.

### Boundary Analyzer

Find room boundary gaps, overlaps and other issues, highlight them in the view and export the results.

**Where to find it:** NexaBIM tab, Room Tools panel, Boundary Analyzer.

**How to use it:**

1. Choose the scope: Active View, Active Level, All Levels or Selected Rooms.
2. Choose the boundary location: Finish, Center, Core Center or Core Boundary, and the gap tolerance.
3. Click Scan.
4. Pick a room on the left. The center shows its Issues or its boundary Segments.
5. Pick an issue to see the detail and use Zoom, Select, Highlight or Isolate.
6. Export to Excel or CSV.

**Features:**

* Issue types: gaps, overlaps, not enclosed, redundant boundaries and unplaced rooms, with severity.
* Segment list with category, element, source, length, room bounding and hidden state.
* Reveal Hidden and Toggle Room Bounding for the element of an issue.
* Highlight Issues and Select Issues for many rooms at once.
* Shaded and colored analysis 3D views, and Delete Analysis Views.
* Reset clears highlights and isolation.

**Tips:**

* Start with the default tolerance and tighten it once the large gaps are fixed.

### Room Finish

Create floors, ceilings and filled regions from room boundaries with type and offset control.

**Where to find it:** NexaBIM tab, Room Tools panel, Room Finish.

**How to use it:**

1. Check the rooms in the list. Use Level, Search, Select all, Invert or Get Selection to pick them.
2. Choose the boundary: Finish Face, Wall Center, Core Face or Core Center.
3. Turn on Floor, Ceiling or Filled Region and choose the type and the height offset for each. For filled regions choose the view.
4. Optionally turn on Skip rooms already finished.
5. Click Create. The Result list shows what was made and why any room was skipped.
6. Select Result selects the created elements.

**Features:**

* Duplicate type creates a new floor, ceiling or filled region type from the chosen one.
* Filled region views: active view, the floor, ceiling or area plan of the room level, or a specific plan.
* Rooms that are not placed, not enclosed or without a closed boundary are reported.
* Each run is one undo step.
* Elements are marked as made by Room Finish so a later run can skip finished rooms.

**Tips:**

* Rooms in linked models are not supported. Open the linked model to finish its rooms.

### Validate

Validate any category against custom parameter rules, then select, isolate, edit or color the results.

**Where to find it:** NexaBIM tab, Room Tools panel, Room Management, Validate.

**How to use it:**

1. Choose a category. Its elements and parameters load automatically.
2. Click Add Rule. Each rule has a parameter, a condition and a value.
3. Choose Match ALL rules or ANY rule.
4. Click Run Validation.
5. Filter the results to All, Pass or Fail. Tick rows and use Select in Revit, Isolate, Edit Parameters or Color Code.
6. Click Export Excel to save the results.

**Features:**

* Conditions: Not Empty, Is Empty, Equals, Not Equals, Contains, Not Contains, Starts With, Ends With, Greater Than, Less Than, Greater or Equal and Less or Equal.
* Value suggestions from the model, and True or False for yes or no parameters.
* Rules can be turned on or off without deleting them.
* Compliance summary with pass, fail and percentage.
* Ticking with All, None and Invert on visible rows, Shift click for ranges and Space for highlighted rows.
* Color Code window that groups elements by level, category, family and type, parameter value or clusters, with Ghost Mode.

**Tips:**

* Color coding reads best in the Shaded visual style.

### Color Code

Color elements in the active view by parameter value with editable color groups.

**Where to find it:** NexaBIM tab, Room Tools panel, Room Management, Color Code.

**How to use it:**

1. Pick a category and click Load Elements.
2. Optionally add filter rules and click Run rules.
3. Under Color By Parameters, select one or more parameters. Use Ctrl for multiple.
4. Click Generate Groups. Each value becomes a color group.
5. Click a swatch to change a color, and turn groups on or off.
6. Click Apply to active view. Clear View removes the overrides.

**Features:**

* Auto Colors, Shuffle, All On, All Off and removing groups.
* Quick Color All loads, groups and applies in one click.
* Surface transparency for the colored elements.
* Ghost Mode fades the elements that are not colored, with a fade strength slider.
* Matched Elements and Unique Elements lists with Select and Isolate.
* Parameter Editor for the loaded elements.
* Export to Excel.
* Clear All Views removes color overrides from every view.

**Tips:**

* F5 loads elements, F6 applies and F7 clears.
* Applying switches the view to Shaded so the colors are visible.

### ElemViz

Chart element data by category and parameter with many chart types, and export charts in high resolution or as SVG.

**Where to find it:** NexaBIM tab, Room Tools panel, Room Management, ElemViz.

**How to use it:**

1. Pick a category and a scope: active view, whole model or current selection.
2. Choose Group by and optionally Then by.
3. Choose the measure: element count, or the sum, average, minimum or maximum of a numeric parameter, with display units.
4. Pick a chart type and adjust Arrange and Display options.
5. Click a chart segment to select or isolate its elements in Revit.
6. Copy the chart image, export the data, or export the chart as PNG or SVG.

**Features:**

* Chart types: column, bar, stacked, stacked 100 percent, grouped, line, area, pie, donut, treemap, scatter, histogram, box plot, waterfall, Pareto, radar, heatmap and summary.
* Quick filter and an advanced filter that uses Element Filter.
* Sorting, top N, grouping the rest as Others.
* Display options: value labels, gridlines, varied colors, percent, average line, trend line, smooth lines, log scale, palette, text size and a custom title.
* Table views Summary, Elements, Statistics and Compare, with mean, median, standard deviation, quartiles and outliers.
* Data export to CSV or Excel.

**Tips:**

* Room Manager can open ElemViz with the rooms already loaded.

## Modelling

### Align

Align elements in a row, a column or by elevation using a 3 by 3 reference point grid.

**Where to find it:** NexaBIM tab, Modelling panel, Align.

**How to use it:**

1. Click Pick and pick the elements in Revit, then click Finish. Or click Selection to use the current Revit selection.
2. Choose what to align to: a picked element, a picked point, the first or last picked element, or the average position.
3. Choose the axis: Horizontal to line up in a row, Vertical to line up in a column, or Elevation Z to match elevation.
4. Click one of the nine reference points, from Top Left to Bottom Right.
5. Click Align.

**Features:**

* Reference by element, by a point on any face, first, last or mean position.
* Several axes can be combined.
* A report of aligned, already aligned, pinned, grouped, view only and failed elements.
* Reset clears everything.

**Tips:**

* Pinned elements and elements in groups are skipped and reported.

### Snap

Drop elements onto floors, faces, toposolids, CAD imports or linked surfaces with a preview first.

**Where to find it:** NexaBIM tab, Modelling panel, Snap.

**How to use it:**

1. Elements: click Pick and pick the elements, then click Finish, or click Selection.
2. Surface: click Pick surface and pick the target. Turn on Linked if the surface is in a linked model.
3. Choose the point that lands on the surface: Bottom, Center or Top, and the tolerance.
4. Click Preview to check each element without moving it.
5. Click Snap.

**Features:**

* Works with floors, sloped faces, topography, CAD imports and elements in linked models.
* Preview with To move, On surface, No hit and Skipped states and the largest move up and down.
* Moves smaller than the tolerance are skipped.
* Result summary of snapped, on surface, no hit and failed elements.

**Tips:**

* Use the preview on large selections to catch elements without a surface below them.

### CAD Import

Link or import DWG and DXF files with layer control, live layer preview and saved layer sets.

**Where to find it:** NexaBIM tab, Modelling panel, CAD Import.

**How to use it:**

1. Click Open and choose a DWG or DXF file. The file is scanned and every layer is listed with its object count.
2. Filter, sort and check the layers you want. Click a layer to highlight it in the preview.
3. Optionally build named sets of layers, or apply a saved preset.
4. Choose Link or Import, then Positioning, Placement, Scope, host view, level, units and colors.
5. Click the Link or Import button at the bottom. Each set becomes its own link or import.

**Features:**

* Layer filter with wildcards, Used and Free filters, and sorting by name, count or checked.
* Live preview with zoom, CAD layer colors or distinct colors, and showing checked layers only.
* In Revit option that highlights the selected layers in the active view.
* Sets: New Set, Add to Set, Rename, Delete, Auto Group by name prefix and Move Next.
* Positioning: Center to Center, Origin to Internal Origin, By Shared Coordinates for links, and Manual Origin.
* Placement in the model or in this view only, with drawing units and color modes Preserved, Black and White or Invert.
* Correct off axis lines.
* Saved layer presets.

**Tips:**

* In a family document CAD files can only be imported.
* Scans are cached for the session, so reopening the same file is fast.

## Coordination

### Clash Detection

Detect clashes between the model and its links, manage them as issues, cut openings and export an Excel report.

**Where to find it:** NexaBIM tab, Coordination panel, Clash Detection.

**How to use it:**

1. Click New Test. In Setup, choose the model for Set A and Set B, the host or a loaded link, and the categories of each set. Add property conditions or skip rules if needed.
2. Choose the clash type: Hard, Clearance or Duplicate, with tolerance, clearance and minimum volume.
3. Click Run Test, or Run All for every test.
4. Review the results. Filter and group them, and click a clash to show it in Revit as Isolate, Ghost or Section Box.
5. Set the status of clashes, Create Issues for them, or plan Openings.
6. Click Excel Report to save the clash report.

**Features:**

* Tests between the host model and loaded links in host coordinates.
* Pairs that belong together by design can be ignored: same assembly, hosted elements, connected MEP, insulation on its run and curtain wall as one.
* Statuses New, Active, Reviewed, Approved and Resolved. Running again keeps status, group and issue for clashes found again.
* Smart Group by floor, model pair, spatial proximity or same element.
* Create Issues sends one issue per clash or per group to the BCF Issue Hub.
* Openings plans and cuts openings in walls, floors, roofs and ceilings, with clearance, rounding, shape and merge rules and a live 3D preview. The cut is one undoable step.
* Dashboard with clash charts. Clicking a bar opens the matching clashes.
* Excel report with summary, every clash and details.
* Clear View resets the clash view.

**Tips:**

* Clash tests are kept for the Revit session. Save the Excel report or create issues to keep a record.

### BCF

Open BCF issues from any platform, review snapshots and comments, jump to their viewpoints and send issues as tickets.

**Where to find it:** NexaBIM tab, Coordination panel, BCF. The window is titled BCF Issue Hub.

**How to use it:**

1. Click Import BCF and choose a BCF file.
2. Use Filters and Saved Views to narrow the list, for example My Issues, Critical, Due Soon or a discipline.
3. Pick an issue. The tabs show Details, Viewpoints, Comments, Clashes, Attachments and History.
4. Click Focus to go to the issue view in Revit, then Isolate, Ghost or Clear.
5. Edit status, priority, assignee, due date and other fields, add comments and save.
6. Create issues with New Issue from the current 3D view or From Selection.
7. Click Export BCF or Excel to share the issues.

**Features:**

* Reads BCF packages from other platforms and keeps every field of packages from NexaIFC Studio.
* Go to issue finds elements by IFC GlobalId and recreates the saved view in a Nexa Issue 3D view.
* 4K viewpoint pictures with a full resolution viewer.
* Assignee register for the people issues can be assigned to.
* Send Ticket creates one ticket in Notion, ClickUp or Trello from the checked issues, with every viewpoint picture. Connections sets up the platforms once for this computer.
* Publish to NexaIFC sends issues to NexaIFC Studio. This button requires NexaIFC Studio and is grayed out with the tip Requires NexaIFC Studio when it is not installed.
* Excel export of the issue list.

**Tips:**

* Issues belong to the Revit session. Export a BCF file to keep them.
* Reset removes every issue of this session and starts fresh.

### Nexa Bridge

Publish the model to NexaIFC Studio and open issues pushed back from it.

**Where to find it:** NexaBIM tab, Coordination panel, Nexa Bridge.

**How to use it:**

1. Install NexaIFC Studio on the same computer. Without it the button is grayed out with the tip Requires NexaIFC Studio.
2. Open Nexa Bridge. The Active Model card shows whether the model is published.
3. Under Publish Session, choose Use active session or Create a new session.
4. Click Publish to NexaIFC, or Publish Update for a model that was published before.
5. Click Open NexaIFC to bring NexaIFC Studio forward, or Issue View to open the Nexa Issue 3D view.
6. Follow progress in the Activity list.

**Features:**

* Publishes the active model to NexaIFC Studio on the same computer.
* Issues sent from NexaIFC Studio arrive in the BCF Issue Hub, even before you open the panel.
* Open Models list and Activity log.
* Locate NexaIFC Studio for a custom install folder.

**Tips:**

* Nexa Bridge talks only to NexaIFC Studio on the same computer.

### Recall

Snapshot the model, compare it with the live model or another snapshot, and restore moved or changed elements.

**Where to find it:** NexaBIM tab, Coordination panel, Recall.

**How to use it:**

1. Name the snapshot, choose the scope by selection or categories, and choose whether to capture parameter values.
2. Click Take snapshot.
3. Later, select a snapshot and compare it with the live model or another snapshot. Set the tolerance and rotation limits.
4. Review the changes: moved, rotated, changed, added or deleted elements with distance and rotation.
5. Use Select, Zoom, Show movement, Heat map and isolate, and Reset view to see the changes in Revit.
6. Click Restore selected or Restore all to put elements back.
7. Export the changes to Excel, CSV or a JSON report.

**Features:**

* Snapshots per model on your computer, identified so they survive renames and local copies.
* Rename, export, import and delete snapshots.
* Property level comparison of parameter values with before and after values.
* Movement markers with a ghost at the saved position and a movement ray.
* Settings for captured parameters, a safety snapshot before restore, and keeping the latest snapshot inside the model.
* View tools to pin or unpin all elements in the view.

**Tips:**

* Keep the safety snapshot before restore turned on so a restore can be undone with Recall too.
* Keeping the latest snapshot in the model makes it travel with the file, but writes data to the model.

## View Tools

### Organize

Create view containers, rename views, apply templates and move views between containers, staged and previewed before anything changes.

**Where to find it:** NexaBIM tab, View Tools panel, Organize. The window is titled View Organizer.

**How to use it:**

1. The left side mirrors the Project Browser. Pick views, a container, or click From Selection to use views selected in Revit.
2. Choose an action tab: Rename, Duplicate, Folders, Templates or Changes.
3. Set up the action and stage it. Staged changes show in the tree right away.
4. Use Undo to remove the last staged change, or Discard to drop everything.
5. Click Apply Changes to write all staged changes in one undoable step.

**Features:**

* Batch rename with a name pattern from name, level, type, family, scale, sheet, phase and discipline, plus find and replace, prefix, suffix, letter case, sequence numbers and cleaning of characters Revit rejects.
* Name check marks empty, invalid, existing and unchanged names.
* View templates with Fits Selection, Apply Template and remove.
* Duplicate views, with detailing or as dependent, in any number of copies.
* Browser folders: create, rename, duplicate and remove containers and move views into them.
* Open a view with Enter, select in Revit and delete views.

**Tips:**

* Nothing changes in the model until Apply Changes.

### View Manager

Rename and duplicate views, assign view templates, rename, duplicate and delete templates, and rename levels.

**Where to find it:** NexaBIM tab, View Tools panel, View Manager.

**How to use it:**

1. On Views, filter by type and search, then pick a view.
2. Enter a new name to rename it, duplicate it with or without detailing, or delete it.
3. Choose a view template and click Assign Template.
4. On View Templates, rename, duplicate or delete templates. Used By shows how many views use each one.
5. On Level Renamer, pick a level and give it a new name.

**Features:**

* View list with name, type, level and template.
* Template list by kind with usage counts.
* Level list with elevations.
* Clear messages when a name is already in use or a template does not fit a view.

**Tips:**

* The active view cannot be deleted. Switch to another view first.

### Section Box

Apply level aware section boxes to 3D views with offsets, presets and copy from another view.

**Where to find it:** NexaBIM tab, View Tools panel, Section Box. The window is titled Section Box Manager.

**How to use it:**

1. Pick the target 3D view. Its current box is shown.
2. Choose Single Level or Multi Level Span.
3. For a single level, pick the level and set the bottom and top offsets. For a span, pick the From and To levels with their offsets.
4. Or click a preset: Floor to Floor, Single Storey, Basement and Ground or Full Storey.
5. Click Apply Section Box.

**Features:**

* Copy From View copies the box height from another 3D view.
* Show or hide the section box outline while clipping stays active.
* Reports when a view template, temporary hide or turned off annotation categories hide the outline, and offers to change the template.

**Tips:**

* Changing a view template affects every view that uses it.

## Help

### About and Help

See the NexaBIM version and support details, read the privacy statement and third party notices, browse every tool and open its online help.

**Where to find it:** NexaBIM tab, Help panel, About or Help. The same two buttons are also on the Add Ins tab, NexaBIM panel. Press F1 while hovering over any NexaBIM ribbon button to open that tool's section of this page.

**How to use it:**

1. Click About to see the product version, the Revit version in use, publisher and support details.
2. Click Help to open the Getting Started steps and the searchable tool directory. Each tool has an Online help link to its section of this page.
3. Open the Privacy page to read how NexaBIM handles your information.
4. Open the Notices page to read the third party components and their full license texts.
5. When you report a problem, click Copy diagnostics on the About page and paste the result into your email.

**Features:**

* About page with product, Revit and runtime versions, install folder, publisher and support contacts.
* Help page with Getting Started, a searchable directory of every tool and links to online help.
* Privacy page with the full privacy statement and buttons that open each local data folder.
* Notices page with every third party component and its full license text.
* Copy diagnostics and Open log folder for support requests.
* Report an issue opens an email to support with your version details filled in.

**Tips:**

* Diagnostics are copied to your clipboard only. Nothing is sent until you paste and send it yourself.
* Inside the About window, press F1 for Help, Ctrl F to search the tool directory and Esc to close.

## Troubleshooting

**The NexaBIM tab is missing after installation.**

* Close Revit fully and start it again.
* Make sure your Revit version is 2024, 2025, 2026 or 2027.
* If Revit asked whether to load the add in, choose to always load it.
* If a NexaBIM Load Error message appeared, it names a log file in %LOCALAPPDATA%\NexaBIM\Logs. Send that file to support.
* Reinstall NexaBIM from the Autodesk App Store if the tab still does not appear.

**A tool button is grayed out.**

* Revit grays add in buttons when no model is open. Open a project.
* Revit grays the ribbon during edit modes such as sketching. Finish or cancel the edit.
* Some tools work only in project models, not in the Family Editor.

**Nexa Bridge or Publish to NexaIFC is grayed out.**

* These need NexaIFC Studio installed on the same computer. The tip Requires NexaIFC Studio confirms this.
* After installing NexaIFC Studio, wait a few seconds or restart Revit so the ribbon picks it up.

**NexaAI does not show in Claude Desktop.**

* Open NexaAI in Revit and go to Connect. Click Connect, or Repair if it says Needs repair.
* If the host shows Missing, click Install host.
* Click Restart Claude. Claude Desktop must restart once to load NexaBIM.
* Keep Revit open. The Revit card must show Running and not Paused.

**Claude can read the model but cannot change it.**

* Model writes are off by default in every Revit session. Turn on Model writes on the Connect page and confirm.

**The NexaAI panel is missing in Dynamo.**

* Start Dynamo from inside Revit. Open the Extensions menu and click NexaAI.
* If the panel was closed, the menu item opens it again.

**A tool says Revit is busy.**

* Finish or cancel the current Revit command with Escape, close open Revit dialogs, then try again.

**A tool asks me to switch back to a model.**

* Tool windows work on the model they were opened from. Activate that model, or close the window and open the tool again in the new model.

**Colors or highlights stay in the view.**

* Use the tool's Reset, Clear View or Reset view button. Then click Refresh View if the screen still shows old graphics.

**An export could not be written.**

* Close the file in Excel or any other program, or choose another folder, then export again.

**Where are my exports?**

* Each tool asks where to save, or uses the output folder shown in its window. 3D Export and Data Export have an Open folder button. Data Export remembers the folder for each model.
* Param Sync issue reports go to Documents, NexaBIM, ParamSync Reports.

**Where are my settings and presets?**

* Settings and presets are in %APPDATA%\NexaBIM. Logs and caches are in %LOCALAPPDATA%\NexaBIM.

**How do I reset a tool's settings?**

1. Close Revit.
2. Open %APPDATA%\NexaBIM and find the file or folder named after the tool. Many tools keep their settings in the Studio folder.
3. Rename or delete it. Deleting the whole NexaBIM folder resets every tool, including saved presets.
4. Start Revit. The tool starts with its defaults.

**How do I report a bug?**

1. Open the About window from the Help panel and click Copy diagnostics.
2. Write an email to er.ndhami1995@gmail.com with what you did, what you expected and what happened.
3. Paste the diagnostics and, if possible, attach the latest log from %LOCALAPPDATA%\NexaBIM\Logs and a screenshot.

**F1 does not open the help page.**

* Hover over a NexaBIM ribbon button until the tooltip shows, then press F1. Your default web browser opens the section of that tool.

## Frequently Asked Questions

**Do I need an account, a license key or an internet connection?**

No. NexaBIM works offline and needs no account. Only NexaAI, which works through Claude Desktop, and sending BCF tickets use the internet.

**Does opening a tool change my model?**

No. Tools read the model when they open. The model changes only when you press an apply, create, write, transfer or run button.

**Can I undo what a tool did?**

Yes. Most tools make their changes as one Revit transaction or one undo step, so Undo in Revit reverses them.

**Does NexaBIM work with workshared models?**

Yes. Tools that edit elements report elements owned by another user, pinned elements and elements in groups instead of forcing a change.

**What is the difference between Prompt Studio and NexaAI?**

Prompt Studio runs fully offline on your computer and understands a library of prompt patterns. NexaAI connects Claude Desktop, using your own Claude account, to Revit and Dynamo for open ended requests.

**Do I need NexaIFC Studio?**

Only for Nexa Bridge and the Publish to NexaIFC button in BCF. Every other tool works without it.

**Are BCF issues and clash tests saved?**

They are kept for the Revit session. Export a BCF file, an Excel report or create issues to keep them after you close Revit.

**Which tools write data into the model besides my own edits?**

Level Filter writes the LevelForFilter parameter. Room Finish and Site Coords store small markers in the model. Recall can keep the latest snapshot in the model if you turn that on. Data Export writes IFC GUIDs only if you choose Store IFC GUID in element parameters.

**Where do I find help for one tool?**

Press F1 on its ribbon button, or open Help on the NexaBIM tab and use the tool directory.

**How do I uninstall NexaBIM?**

Close Revit and uninstall NexaBIM from the Autodesk App Store manager or from Windows Settings, Apps. To remove settings, logs and the NexaAI files too, follow [Uninstalling](#uninstalling).

## Privacy

Effective date: 13 October 2026.

NexaBIM runs inside Autodesk Revit on your computer. We do not collect, sell or share your personal information. The same statement is built into NexaBIM under About, Privacy.

**Summary**

* No account and no sign in.
* No telemetry, analytics, advertising or tracking.
* No license checks and no update checks.
* Your model data stays on your computer.
* Data leaves your computer only when you send it to a service you connected.

**Who is responsible**

NexaBIM is responsible for this statement. Contact details are at the end of this section.

**Information we collect**

* **None through the software.** NexaBIM sends no telemetry, analytics, usage statistics or crash reports to us or to anyone else, and contains no third party analytics, advertising or tracking code.
* **When you contact us.** If you email us, we use your email address and what you send, such as diagnostics or log files, only to answer you. We keep it only as long as needed to resolve your request and delete it when you ask.
* **Autodesk App Store.** Autodesk runs the App Store, your Autodesk account, downloads and any payment under the Autodesk Privacy Statement. Customer details Autodesk shares with us as the publisher, such as a purchaser email address, are used only for support and to fulfil the purchase.

**What starts with Revit**

These parts start or are prepared when Revit starts. All of them stay on this computer and none of them sends anything over the internet.

* **NexaAI bridge.** Starts with Revit so Claude Desktop can reach the open session. It listens only on a local named pipe restricted to your Windows user and protected by a token that is new for every session, and does nothing until Claude Desktop sends it a request through the NexaBIM MCP host. While Revit runs, a session file in %LOCALAPPDATA%\NexaBIM\NexaAI\Sessions holds the pipe name and token, the Revit and NexaBIM versions, your Windows user name, the open document title and active view name. It is deleted when Revit closes. Turn off **Start with Revit** on the Connect page of the NexaAI window to stop the bridge from starting.
* **NexaBIM MCP host.** The first time Revit starts, NexaBIM copies its MCP host program to %LOCALAPPDATA%\NexaBIM\McpHost. It runs only when Claude Desktop starts it after you connect NexaAI.
* **NexaAI for Dynamo.** The first time Revit starts, NexaBIM copies the NexaAI for Dynamo package to your Dynamo packages folder. It is active only in a Revit session where NexaBIM is loaded.
* **Nexa Bridge.** Checks for NexaIFC Studio on this computer over a local loopback connection. It never connects to another computer.

**Optional connected features**

These features send data off your computer only after you connect them, and only when you ask.

* **NexaAI with Claude Desktop.** When you ask Claude to read from Revit, the results you request, such as element data, parameter values, document titles, file paths and view images, are sent by Claude Desktop to Anthropic under your own Claude account and the Anthropic privacy policy. NexaBIM itself sends nothing to Anthropic. Model changes by Claude are off by default at the start of every session until you allow them. Only when you choose Connect does NexaBIM add or repair a NexaBIM entry in the Claude Desktop configuration file, keeping up to five backups of that file next to it. After that, it keeps the entry pointing at the current MCP host when Revit starts.
* **BCF tickets.** Issues are sent to Notion, ClickUp or Trello only when you connect a platform and click Send Ticket. The issue fields, comments, images, attachments and element identifiers go to that service under your account and its own terms. Access tokens are encrypted with Windows data protection for your Windows user and stored in %APPDATA%\Nexa.
* **Nexa Bridge with NexaIFC Studio.** Exchanges models and issues with NexaIFC Studio through files in %LOCALAPPDATA%\NexaIFC Studio and a local loopback connection on the same computer. Nothing leaves your computer.

**Third parties**

We do not sell, rent or give your information to anyone. Data you send with a connected feature goes directly from your computer to the service you chose, under your own account with that service, and NexaBIM sends only what you ask it to send. NexaBIM connects only to services that publish their own privacy commitments: Anthropic, Notion, ClickUp and Trello. Their privacy policies apply to the data you send them, and they are responsible for protecting it.

**Files on your computer and how long they are kept**

* Settings, presets and Recall snapshots: %APPDATA%\NexaBIM, kept until you delete them.
* Logs: %LOCALAPPDATA%\NexaBIM\Logs. Logs record tool activity and errors and can include file paths and document names. Each log file is deleted after 30 days.
* NexaAI sessions and settings, the MCP host program and caches: %LOCALAPPDATA%\NexaBIM. Session files are deleted when Revit closes.
* Ticket connections: %APPDATA%\Nexa, kept until you disconnect the service.
* Nexa Bridge exchange: %LOCALAPPDATA%\NexaIFC Studio.
* NexaAI for Dynamo package: the packages folder of each Dynamo version under %APPDATA%\Dynamo\Dynamo Revit.
* Claude Desktop entry: %APPDATA%\Claude\claude_desktop_config.json, only after you connect NexaAI.
* Temporary files: the Windows temp folder, removed when the task ends or by Windows.
* Files you export go only to the folders you choose.

**What is written into your model**

NexaBIM changes your model only through tools you run. Besides the edits you ask for, these tools may store data in the model:

* Level Studio writes the LevelForFilter shared parameter.
* Room Finish and Site Coords store extensible storage markers.
* Recall stores the latest snapshot in the model only if you turn that option on.
* Data Export writes IFC GUIDs to element parameters only if you choose that option.

**Your choices and consent**

* **NexaAI bridge:** turn off Start with Revit on the Connect page of the NexaAI window.
* **Claude Desktop:** remove the NexaBIM entry under mcpServers in %APPDATA%\Claude\claude_desktop_config.json and restart Claude Desktop.
* **Notion, ClickUp or Trello:** choose Disconnect in the BCF tickets settings, then revoke the token in that service.
* **Data already sent:** ask Anthropic, Notion, ClickUp or Trello to delete it under their own policies. We hold no copy, so there is nothing for us to delete.

To remove everything NexaBIM stored, follow [Uninstalling](#uninstalling).

**Children**

NexaBIM is professional software for building design and is not directed at children. We do not knowingly collect information from anyone, including children.

**Changes to this statement**

When this statement changes, the new version ships with NexaBIM and is published here with a new effective date.

**Contact**

NexaBIM, er.ndhami1995@gmail.com.

## License

NexaBIM is copyright © 2026 NexaBIM. All rights reserved.

NexaBIM is licensed to you under the Autodesk App Store end user license agreement shown when you install it. The third party components listed below keep their own licenses. Nothing in the NexaBIM license agreement limits the rights the GNU Lesser General Public License gives you for ProjNET: you may replace ProjNET.dll with a compatible build, and you may modify NexaBIM for your own use and reverse engineer it as far as needed to debug such modifications, as section 6 of that license requires.

## Third Party Notices

NexaBIM includes or uses the components below. Each is the property of its owners and is provided under its own license. The full license texts are included with the product and shown on the Notices page of the About window.

* **ProjNET** version 2.1.0, copyright NetTopologySuite Team and Morten Nielsen. GNU Lesser General Public License version 2.1 or later. Used for coordinate system definitions and transformations in Site Coords and Location Info. Shipped unmodified as a separate file that you may replace with a compatible build as the LGPL permits; see [License](#license) for your LGPL rights. Source: [ProjNET on GitHub](https://github.com/NetTopologySuite/ProjNet4GeoAPI).
* **NetTopologySuite**, the project that maintains ProjNET.
* **Microsoft .NET libraries and runtime**, copyright .NET Foundation and Contributors. MIT License. System.Memory, System.Buffers, System.Numerics.Vectors and System.Runtime.CompilerServices.Unsafe in the Revit 2024 build, and the .NET runtime included in the self contained NexaBIM MCP Host. Source: [.NET runtime on GitHub](https://github.com/dotnet/runtime).
* **EPSG Geodetic Parameter Dataset**, owned by IOGP, the International Association of Oil and Gas Producers. The coordinate system catalog of Site Coords and Location Info is derived from it. Terms of use: [epsg.org terms of use](https://epsg.org/terms-of-use.html).
* **Revit IFC default category mapping**, copyright Autodesk, Inc., from the [Autodesk Revit IFC project](https://github.com/Autodesk/revit-ifc). GNU Library General Public License version 2. Used as the default IFC class to Revit category mapping in Data Export.

**Trademarks**

Autodesk, Revit, Dynamo and Navisworks are registered trademarks or trademarks of Autodesk, Inc. Claude is a trademark of Anthropic PBC. Notion, ClickUp and Trello are trademarks of their respective owners. NexaBIM is not affiliated with or endorsed by these companies.

## Support

* Email: er.ndhami1995@gmail.com
* Help page: [NexaBIM Help Section](https://github.com/07naresh07/NexaBIM_HelpSection)
* Publisher: NexaBIM

When you write, please include:

* Your Revit version and the NexaBIM version from the About window.
* The diagnostics from Copy diagnostics in the About window.
* The steps to reproduce the problem and a screenshot if possible.
* The latest log file from %LOCALAPPDATA%\NexaBIM\Logs.
