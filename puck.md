# Puck

Puck is a refactoring tool.

# Installation

Puck depends on graphviz to compute the layout of the diagram class. You can either set the location of dot in the settings pannel or be sure that dot is in the env PATH variable.

# Quick Start

A Puck workspace is the directory containing its project. Sources can be placed in any subdirectory except for one that is named out. By default Puck will search a decouple.pl file at the root of the workspace. This is the file containing the weland coupling constraint. Also at the root of the workspace, you can put a jar.list file containing a list (one by line) of absolute paths toward jars outside of the workspace. You can select the work space with the eponym button. Upon selection it will automatically (1) search for java sources and jar archives, (2) build a dependency graph, and (3) load the coupling constraints. Puck default workspace is the current directory, if it suits you, you will just have to click on the ``(Re)load code and constraints'' button. Constraints have to be edited externally and can be reloaded with the ``(Re)load constraints'' button.
Once the dependency graph builded, you can click on the show graph button to open the interactive browser. Please note that we are experiencing some graphviz crashes in the layout computation. If you want to display a large graph, think to click before the ``Package visibility'' button. On the browser opening only packages will be displayed but you can then select more precisely which element to show as explained below in the Visual options section. Alternatively to the ``Show graph'' button you can click on ``Focus on violations''. This will ignore any node selections and display only the sources and targets of every violations with ther containers. If there is no violations nothing will be displayed.

# Transformations

The following categories of transformations are at your disposal.

## Intro
For now, only packages, classes and interfaces can be directly introduced. You just have to right-click on the future container and choose add [...] in the contextual menu. To add top level packages you need to click the ``Add package'' button in the bottom of the screen.

## Abstract
You can right-click on any abstractable element (i.e any element except packages) and choose ``Abstract as ...'' in the contextual menu.

## Redirection - ''Use instead''
Redirect, that is uses an element instead of another currently used is performed as follow : first select the uses to redirect (left-click) and then right-click on the new element to uses and select in the contextual menu ``Use this instead of ...''.

## Move
To move an element, you have to select it (left-click on its name), then right click on his future new container and finally select ``Move [...] here'' in the contextual menu.

## Merge
To merge an element with another, first select the element you want to see disappear. Second right-click on the other merging element and select in the contextual menu ``Merge into this''.

## Rename
Right-click > Rename

## Delete
This action is only available for unused node (no incomming uses arc). Right-click > Delete
For code generation, see Other Actions.

# Visual options
Some options are available in the starting screen before opening the browser. In the middle column of this screen you can see a tree explorer of your project. Any selected element will be displayed in the browser and every unselected one will be hidden. The ``Package visibility'' button will select every packages and only them while the ``Package+Class visibility'' will also select every classes but not the methods nor the fields.
Once in the browser you can right click on an element to access to the following options:

* Collapse
hide every elements contained by the selected one.
* Hide
collapse and hide also the selected one.
* Expand
display only direct content of the selected element.
* Expand All
display every elements recursively contained by the selected one.

# Checkboxes

* Show signatures : Display methods' signatures.
* Show ids : Display internal node Ids. Essentially usefull for debugging purposes.
* Show Virtual Edges : Show the existence of dependency between hidden elements by displaying a dotted edge between their first visible parents.
* Concrete Uses/Virtual Edge : Show on each virtual edges how many concrete uses they depict.
* Show Red Only : Show only red edges.

# Shortcuts:

* Ctrl++ and Ctrl+- to zoom in or out.
* Ctrl+Left click to select a zone to zoom in
* Hold Shift+Left click to move the image

# Other actions

## Refactoring Plan

Once you have performed some of the actions described above on the dependency graph, you can save the refactoring plan using the "Save" button. Later on, you can load this file if you generate the dependency graph of the same starting code. The loaded refactoring plan is entirely applied but you can use the undo/redo buttons to reenact each step. You can display in a human readeable form the refactoring plan using the "Show recording" button.

## Code generation

At any time you can apply the refactoring plan i.e. generate the code with the apply button. The code is generated in an "out" folder at the root of the project workspace. Please note that the undo/redo button are only linked to the dependency graph. Once the code generated, if you want to do other transformations, or load a refactoring plan, you will have to reload the code first.

If you check the "test commutativity" checkbox before applying the refactoring plan, puck will also compile the generated source, produce a dependency graph and compare it with the graph obtained from the refactoring plan.

[home page](index.md)

