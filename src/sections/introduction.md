# User Plugin Format Documentation

## Introduction to Pedal Games user plugins

The user plugin module and the user plugin format is designed to enable users extend Pedal Games with their own data panels and to make it possible to include data in the user interface beyond those data fields pre-defined by Pedal Games.

### Purpose

The primary purpose of the user plugin format is to facilitate the development of plugins that can enhance the application's capabilities. By adhering to this format, developers can ensure that their plugins are compatible with the application and can be easily managed and utilized by end-users.

### Utilisation

Developers can utilise the user plugin format by creating JSON or JSON5 files that define the plugin's properties, fields, templates, and display settings. These files should be placed in the designated plugins directory within the user's home folder. Once the plugins are defined, they can be loaded and executed by the application, providing users with additional features and functionalities.

This documentation will guide you through the various aspects of the user plugin format, including its structure, field definitions, templates, display properties, and validation criteria. 

### Loading plugins in Pedal Games

The user plugin folder where all plugins must be placed is

``
%userprofile%\pedal-games\plugins
``

You can use subfolders to organise your plugins and avoid naming conflicts if you get Pedal Games plugins from different sources.