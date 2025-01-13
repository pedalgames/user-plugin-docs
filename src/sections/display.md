# Display Properties of User Plugins

## Overview

The display properties of a user plugin define how the plugin will be presented within the application. This includes the layout, style, and content that will be rendered to the user. 

## Display String Format

The display string is an HTML fragment that can include various HTML elements. It should be structured to provide clear information to the user. The following elements are commonly used:

- `<div>`: For block-level content.
- `<span>`: For inline content.
- `<h1>`, `<h2>`, etc.: For headings.
- `<p>`: For paragraphs.
- `<br>`: For line breaks.
- `<hr>`: For horizontal rules.
- `<img>`: For images.
- `<style>`: For inline CSS styles.

### Example

```html
<div>
    <h1>{{plugin.name}}</h1>
    <p>{{plugin.description}}</p>
    <div style="color: red;">This is a custom message.</div>
    <div><span data-field="hr"></span><div>
    <div><span data-plugin-field="zwiftlog/chat" data-plugin-lines="10" data-plugin-order="reverse"></span><div>
    <div><span data-plugin-field="zwiftlog/pacepartner"></span><div>
</div>
```

Placeholders `{{plugin.id}}`, `{{plugin.author}}`, `{{plugin.name}}`, `{{plugin.description}}` will be replaced with the actual plugin values when rendered.

## Constraints

When defining the display properties, ensure the following constraints are met:

1. **Valid HTML**: The display string must be a valid HTML fragment. All elements should be properly closed.
2. **Multiple Root Elements**: The fragment can contain multiple root elements, but they should be wrapped in a single parent element.
3. **Allowed Elements**: Only the specified HTML elements are allowed. Avoid using scripts or unsupported tags.
4. **Styling**: Inline styles can be used, but they should not conflict with the overall application styling.

## Validation

The display string will be validated to ensure it meets the criteria outlined above. If the validation fails, a default message will be displayed instead.
