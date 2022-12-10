# Essay 4 - Team 7
## Godot's Plugin System
### Authors: Alberto Gomez-Han, Jon González, Alexander Reynolds, Ryan Tullis 

#### Introduction
Godot supports extensibility via its plugin system which, a project wide system that has its own database, web services, and which is a drawing feature of Godot. While The Godot Project maintains its own
official Asset Library, the editor supports the use of any plugin that conforms to their specifications and can be installed by users manually. One powerful feature of Godot's
plugin system is that plugins do not need to be compiled or written in a standalone programming language, and can be built using the editor, written in GDScript, Godot's
proprietary scripting language. In fact, the Editor allows you to create plugins much like it supports the creation of scenes and other assets, featuring its own menu
for doing so. This robust support for plugins demonstrates the project's commitment to ensuring high configurability by end-users, a subject discussed in our previous essay. For this deeper
analysis, we will start with discussion of what specific enhancements are supported by the plugin system.

#### Asset Library
Godot provides an Asset Library that the community may contribute to. The barrier of entry is fairly low, requiring only registration on their website in order to begin contributing plugins to the library. Once a plugin is submitted to the Asset Library, Godot maintainers review the plugin before formally making it available to other users for download. The Asset Library features plugins that are pending review, leaving them open for comments from the wider community. The Asset Library is not only accessible via a website, but direct downloading of plugins is available via the Editor, providing a more streamlined installation process as opposed to manually inserting unzipped files into the '/addon' directory. The plugin system gives the community the ability to create specialized UI components for unique or common problems. Godot puts in the effort to host the Asset Library because by connecting all the users and allowing them to share plugins, Godot ensures that people are constantly adding new features to Godot, even if just trhough the plugin store. This allows for many more spefic variations of Godot for specific kinds of projects and gives Godot a level of configurability that Godot's competitors don't have.


#### Asset Library Database
The Asset Library has a database that hosts the creations of users: art, music, plugins, etc. Godot editor by default supports connection to the Asset Library database, and encourages users to download helpful plugins and to add their own work. This public collection of assets connects the Godot community. Contributions to Godot's Asset Library are rarely removed, This means the size of the Asset Library will mainly only get grander and as it does the users it pulls in will help increase the Asset Library's growth rate. 

The Godot Project maintainers have implementd submission guidelines to the Asset Library to ensure the quality of the plugins that live in the database. These requirements range from the asset actually working, to using proper English for the name and descritpion of the plugin. The maintainers also recommend to anybody creating a plugin to conform to the official style guides of Godot and to add a copy of their license and a readme file to the plugin folder, that way users who use download their plugins can fulfill licensing terms and learn how to properly use the plugin.

#### Plugin Nodes
The Godot Editor supports the creation of entirely new UI menus and features by leveraging its node system, which is also utilized to render its games. Indeed, the plugin system makes extensive reuse of already-implemented features, allowing the Godot plugins to be created and edited within the Godot editor itself.

Nodes come in several different types,and are used to represent things like scenes, graphical assets, and 3D objects. Custom node types can be created as part of a plugin by writing a script containing the logic that will back that type. These scripts can be written in any scripting language, but the Godot documentation recommends using either GDScript or C#. Once this is done, the new node type can be registered as a class in the editor's Script Class system, which enables the creation of nodes using that backing script logic. 

#### Editor Plugins
Through the plugin system, new screens, buttons, and other UI elements can be added to the editor, extending each with additional functionality as needed. For these UI elements, the new node custom type must extend the 'Control' class. This node custom type can also integrate other native nodes, such as Buttons. As these custom types are treated as classes by Godot, they can also inherit from any other class desired, meaning that plugins installed by end-users can themselves be extended with increased functionality. Graphical assets to be used by these plugins can also be added to the plugin's folder in '/addons', allowing them to be pre-loaded when the Editor initializes, providing a way for users to include custom graphics, themes, and effects.
