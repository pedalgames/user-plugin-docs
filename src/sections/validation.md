# Validation of User Plugins

This section outlines the validation process for user plugins, detailing the criteria that must be met for a plugin to be considered valid.

## Validation Criteria

A user plugin is considered valid if it meets the following criteria:

1. **ID**: 
   - Must be a non-empty string in the format `xxx/yyy`, where `xxx` is the plugin author and `yyy` is the plugin name.
   - The ID must be unique among all plugins.
   - Allowed characters include letters, numbers, '.', '-', and '_'.

2. **Description**: 
   - Must be a non-empty string that provides a brief overview of the plugin's functionality.

3. **Name**: 
   - Must be a non-empty string that represents the name of the plugin.

4. **Tags**:
   - An optional array of strings.
   
5. **Fields**: 
   - An array of strings representing field names. If provided, it should contain valid field names.

6. **Template**: 
   - An optional string that specifies the template to be used. It must be a non-empty string and match one of the known template names: `default`, `block`, or `bit`.

7. **Display**: 
   - An optional string that defines how the plugin will be displayed. If provided, it must be a valid HTML fragment.

8. **Field Definitions**: 
   - Each field definition must include:
     - **value**: A string with the id of the field to display (either a standard Pedal Games field or a field `plugin/field` getting its data from the HTTP server interface of Pedal Games.
     - **Lines**: A number greater than 0 (default is 1).
     - **Chronological**: A boolean indicating the sorting order (optional).
   - Each field definition can include:
     - **label**: A string.
     - **sublabel**: A string.
     - **unit**: A string.
     - **lines**: A number greater than 0 (default is 1). Indicates that the field is a text field with multiple lines.
     - **order**: A string determining the order of the lines in a multiple line field. 'reverse' means the newest line at top (optional).
     - **description**: A string.
     - **color**: A string with a valid CSS color code or color name.

## Validation Process

The validation process involves checking each of the above criteria. If any criterion is not met, the plugin will be deemed invalid. The validation function will log errors for any issues encountered during the validation process, allowing you to identify and rectify problems efficiently.

The validation log is ``%appdata%\pedal-games\logs\plugin.log``.
