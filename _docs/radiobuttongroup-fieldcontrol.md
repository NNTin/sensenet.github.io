---
title: "RadioButtonGroup Field Control"
source_url: 'https://github.com/SenseNet/sensenet/blob/master/docs/radiobuttongroup-fieldcontrol.md'
category: Development
version: v6.0
tags: [radiobutton, radiobuttongroup, choice, field control, field]
description: The RadioButtonGroup Field Control displays a list of radiobuttons for selecting an option from a single-selection Choice field.
---

# RadioButtonGroup Field Control

The RadioButtonGroup Field Control displays a list of radiobuttons for selecting an option from a single-selection Choice field.

<img src="https://raw.githubusercontent.com/SenseNet/sensenet/master/docs/images/Radiobuttongroup.png" style="margin: 20px auto" />

When the underlying [Choice Field](/docs/choice-field) is configured to allow extra value an extra textbox is rendered next to the radiobuttongroup control.

## Supported Field types

- [Choice Field](/docs/choice-field)

## Properties

- **SelectedValueType** (optional): Sets the display type of the selected options in *Browse* mode. Possible values are *Value* and *Text*, default is *Text*.

Example:

```html
   <sn:RadioButtonGroup ID="RadioButtonGroup1" runat="server" FieldName="Style" SelectedValueType="Value" />
```

## Templates

The RadioButtonGroup Field Control renders a Label control in Browse mode and a RadioButtonList accompanied with a TextBox - the latter for an optional extra value - in Edit mode.

### Browse view template

```csharp
<%@  Language="C#" %>
<asp:Label ID="InnerControl" runat="server" />
```

### Edit view template

```csharp
<%@  Language="C#" %>
<asp:RadioButtonList CssClass="sn-ctrl sn-ctrl-radiogroup" ID="InnerControl" runat="server" />
<asp:TextBox CssClass="sn-ctrl sn-ctrl-text sn-ctrl-extravalue" ID="ExtraTextBox" runat="server" />
```

## Examples

### Simple example

```html
   <sn:RadioButtonGroup ID="RadioButtonGroup1" runat="server" FieldName="Style" />
```

### Templated example

```html
   <sn:RadioButtonGroup ID="RadioButtonGroup1" runat="server" FieldName="Style">
      <EditTemplate>
         <asp:RadioButtonList ID="InnerControl" runat="server" />
         <asp:TextBox ID="ExtraTextBox" runat="server" />
      </EditTemplate>
   </sn:RadioButtonGroup>
```