# Field Definitions in User Plugins

Field definitions are a crucial part of the user plugin format, as they specify the attributes and characteristics of each field within a plugin. Each field can have various properties that dictate its behavior and presentation. Below are the key attributes that can be defined for each field:

## Field Attributes

1. **id** (string, required)
   - A unique identifier for the field. This should be a descriptive name that clearly indicates the purpose of the field.

2. **label** (string, required)
   - The label that will be displayed to the user. This should be concise and informative.

3. **sublabel** (string, optional)
   - An additional label that provides further context or information about the field. This can be used to clarify the purpose of the field.

4. **unit** (string, optional)
   - The unit of measurement for the field's value, if applicable (e.g., "W" for watts, "bpm" for beats per minute).

5. **type** (string, required)
   - The data type of the field. This can be either "text" or "number", indicating the kind of input expected from the user.

6. **lines** (number, optional)
   - Specifies the number of lines for text fields. The default value is 1.

7. **order** (string, optional)
   - If set to `reverse`, the field will be sorted in reverse chronological order, otherwise it will be sorted chronologically. The default is chronological order.

8. **value** (string, required)
   - The key that corresponds to the value being represented by the field. This should match the field names defined in the plugin.

9. **description** (string, optional)
   - A brief description of the field's purpose or usage. This can help users understand how to interact with the field.

10. **color** (string, optional)
    - A color code or name that can be used to style the field visually. This can enhance the user interface and improve usability.

11. **style** (string, optional)
    - Will be added to the style attribute of the HTML element surrounding the field in the output. It is possible to control some styling via CSS attributes (or CSS variables) set in the **style** property: `--label-font-size`, `--label-color`, `--field-font-size`, `--field-line-height`, `--field-font-weight`

## Example Field Definition

Here is an example of how a field definition might look in a user plugin:

```json
{
    "id": "field1",
    "label": "Field 1",
    "sublabel": "Sublabel 1",
    "unit": "W",
    "lines": 1,
    "chronological": true,
    "value": "power-instant",
    "description": "Instantaneous power output",
    "color": "red"
}
```

Here is another example, showing field definitions in the context of a plugin defition:

```json
{
	"id": "jrn/zwiftlog-chat-simple-block",
	"author": "Jesper Nielsen",
	"version": "0.1",
	"description": "Output a chat message (string)",
	"name": "Plugin jrn/zwiftlog-chat-simple-block",
	"fields": [ '$zwiftlog/chat' ],
   "fieldDefinitions": {
        "$zwiftlog/chat": {
            "label": "Chat",
			   "sublabel": "Messages:",
			   "value": "zwiftlog/chat",
            "lines": 3,
            "style": "width: 600px; height: 200px; --field-font-size: 10px; --field-line-height: 12px; --field-font-weight: normal;",
            "order": "reverse"
        }
    },
    "template": "block",
}
```

