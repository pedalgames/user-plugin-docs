# User Plugin Structure

The structure of a user plugin is defined by a set of required and optional properties. Each plugin must adhere to the specified format to ensure proper functionality within the application. Below is an outline of the overall structure of a user plugin, detailing the required properties and their expected formats.

## Required Properties

1. **id**: 
   - Type: String
   - Format: Must be in the format `author/plugin-name`, where both `author` and `plugin-name` can contain letters, numbers, '.', '-', and '_'. The `id` must be unique among all plugins.

2. **name**: 
   - Type: String
   - Description: A human-readable name for the plugin. This should not be empty.

3. **description**: 
   - Type: String
   - Description: A brief description of the plugin's functionality. This should not be empty.


## Optional Properties

1. **fields**: 
   - Type: Array of Strings
   - Description: An array of fields that the plugin will use. An item in item must be the name of field exposed by Pedal Games, a plugin field characterized by name `plugin/field`, or a reference to a field definition in the fieldDefinitions property in the format `$<fieldDefName>`.
   - Notes: Only together with **template**.

2. **grid**: 
   - Type: String
   - Format: Should be in the format `columns/rows`, indicating the layout of the plugin in the UI. 
   - Notes: Only together with **template**.

3. **fieldDefinitions**: 
   - Type: Object
   - Description: An object defining the attributes for each field used in the plugin. Each field can have its own set of properties, such as `label`, `sublabel`, `unit`, `value`, `description`, and `color`.
   - Notes: Only together with **template**.

4. **template**: 
   - Type: String
   - Description: The name of the template to be used for the plugin. This is optional and should match one of the known template names (e.g., 'default', 'block', 'bit').

5. **display**: 
   - Type: String
   - Description: A string that defines how the plugin will be displayed in the UI. This can include HTML fragments and should be validated to ensure it is a proper HTML structure. Where the fields will be inserted is controlled with data-field and data-plugin-field attributes to HTML elements.
   - Notes: To enable the use of a multiline string for the value of display without having to escape the line breaks as otherwise required in the JSON5 format, we allow you to wrap the string in triple quotes like this: ``'''<multiline string>'''``. 

Either **template** or **display** must be present.

## Example Structure

Using the template 'default':

```json
{
    "id": "plugin/author-name",
    "name": "Example Plugin",
    "description": "This is an example plugin.",
    "fields": [ "power-instant", "plugin/number", "$field1", "$field2"],
    "template": "default",
    "grid": "2/1",  // two columns
    "fieldDefinitions": {
        "field1": {
            "label": "Field 1",
            "unit": "units",
            "value": "cadence-instant",
            "description": "Description for field 1",
            "color": "red"
        },
        "field2": {
            "label": "Field 2",
            "unit": "units",
            "value": "plugin/text",
            "description": "Description for field 2",
            "color": "blue"
        }
    }
}
```
## Example Structure

Using the **display** property:


```json
{
    "id": "plugin/author-name",
    "name": "Example Plugin",
    "description": "This is an example plugin.",
    "display": '''
    <style>
    .number { color: red; }
    </style>
    <div>Plugin Display</div>
    <p class="number"><span data-field="power-instant"></span></p>
    <p class="number"><span data-plugin-field="plugin/field1"></span></p>
    <p class="number"><span data-field="cadence-instant"></span></p>
    <p class="number"><span data-field="hr"></span></p>
    '''
}
```

This structure ensures that the user plugin is well-defined.