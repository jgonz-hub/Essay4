# Essay 4 - Team 7
## Godot's Plugin System
### Authors: Alberto Gomez-Han, Jon González, Alexander Reynolds, Ryan Tullis 

#### Introduction
Godot supports extensibility via its plugin system which, like the core project, includes various modules developed by the community. While The Godot Project maintains its own
official Asset Library, the editor supports the use of any plugin that conforms to their specifications and can be installed by users manually. One powerful feature of Godot's
plugin system is that plugins do not need to be compiled or written in a standalone programming language, and can be built using the editor, written in GDScript, Godot's
proprietary scripting language. In fact, the Editor allows you to create plugins much like it supports the creation of scenes and other assets, featuring its own menu
for doing so. This robust support for plugins demonstrates the project's commitment to ensuring high configurability by end-users, a subject discussed in our previous essay. For this deeper
analysis, we will start with discussion what specific enhancements are supported by the plugin system.

#### Asset Library
Godot provides an Asset Library that the community may contribute to. The barrier of entry is fairly low, requiring only registration on their website in order to begin contributing plugins to the library. Once a plugin is submitted to the Asset Library, Godot maintainers review the plugin before formally making it available to other users for download. The Asset Library features plugins that are pending review, leaving them open for comments from the wider community. The Asset Library is not only accessible via a website, but direct downloading of plugins is available via the Editor, providing a more streamlined installation process as opposed to manually inserting unzipped files into the '/addon' directory.

#### Plugin Nodes
The Godot Editor supports the creation of entirely new UI menus and features by leveraging its node system, which is also utilized to render its games. Indeed, the plugin system makes extensive reuse of already-implemented features, exposing them for the custom use of plugin developers.

Nodes come in several different types,and are used to represent things like scenes, graphical assests, and 3D objects. Custom node types can be created as part of a plugin by writing a script containing the logic that will back that type. These scripts can be written in any scripting language, but the Godot documentation recommends using either GDScript or C#. Once this is done, the new node type can be registered as a class in the editor's Script Class system, which enables the creation of nodes using that backing script logic. Through this, new screens, buttons, and other UI elements can be added to the editor, extending each with additional functionality as needed. For these UI elements, the new node custom type must extend the 'Control' class. This node custom type can also integrate other native nodes, such as Buttons. As these custom types are treated as classes by Godot, they can also inherit from any other class desired, meaning that plugins installed by end-users can themselves be extended with increased functionality. 
