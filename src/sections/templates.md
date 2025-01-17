# Templates for User Plugins

User plugins can utilize various templates to define their structure and presentation. Each template has a specific graphical style. Below are the available templates and their descriptions:

## 1. Default Template

The default template is the simplest form of presentation for user plugins. It is designed to display basic information. It support a grid format.

### Implementation

To use the default template, specify it in the plugin definition as follows:

```json
{
    "template": "default"
}
```

## 2. Block Template

The block template allows for a layout in the style of the Block data panels from Pedal Games. It allows showing the fields in a grid format.

### Implementation

To implement the block template, include it in the plugin definition:

```json
{
    "template": "block",
    "grid": "2/1"
}
```

The `grid` property defines the number of columns and rows for the layout.

## 3. Bit Template (TO BE IMPLEMENTED)

The bit template allows for a layout in the style of the Bit data panels from Pedal Games. It allows showing the fields in a grid format.

### Implementation

To utilize the bit template, specify it in the plugin definition:

```json
{
    "template": "bit"
}
```

## Customization

Each template can be customized further by defining specific styles and modes. Refer to the field definitions and display sections for more details on how to enhance the appearance and functionality of your user plugins.
