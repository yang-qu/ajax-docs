---
title: Custom Stylization
page_title: Custom Stylization | UI for ASP.NET AJAX Documentation
description: Custom Stylization
slug: editor/managing-content/content-area-appearance/custom-stylization
tags: custom,stylization
published: True
position: 1
---

# Custom Stylization



Customizing the RadEditor’s content could be achieved with two properties __ContentAreaCssFile__ and __CSSFiles__.The values of this properties are the relative path to a CSS file, where are placed the styling rules for the default design of the content area.

>warning Both properties work only in __ContentAreaMode="Iframe"__ mode. In __“DIV”__ mode the content areastylization should be done with ordinary link to the CSS file in the __head__ element using the __.reContentArea__ as parent for all desired child elements in the CSS selectors.
>


## Differences between the two approaches

When it comes to stylization for the default design rules there are no differences in the setup for the both approaches. Using CSS selectors of HTML elements will set the default CSS rules for the content. For example to change the background color of the content area, the CSS file for both approaches will look like that:

````XML
	    body
	    {
	      background-color: red;
	      background-image: url(image_path);
	      color: black;
	    }
````



The biggest difference is that the __ContentAreaCssFile__ property is intended for default settings like the example above and using custom class names(Example: __.redText__) in the CSS selectors will not affect the content design.

As for the __CSSFiles__ property - it is created so that the users could choose different predefine set of class names,populated from the CSS file/s or override from the __CssClasses__ property. This class names could be selected from a dropdown menu(__Apply CSS class__ tool) for the desired element in the content and with that to change its class name and respectively the stylingand/or formatting with predefined styling rules from the pointed CSS file.

The following example shows how to set a default body background and an option in the __Apply CSS class__ dropdown for text with white color:

````XML
	    <telerik:radeditor runat="server" id="RadEditor1">
	        <CssFiles>
	            <telerik:EditorCssFile Value="~/ContentAreaCssFile.css" />
	        </CssFiles>
	        <CssClasses>
	            <telerik:EditorCssClass Name="Black text" Value=".blackText" />
	        </CssClasses>
	    </telerik:radeditor>
````



````XML
	    body
	    {
	        background-color: red;
	        color: white;
	    }
	
	    .blackText 
	    {
	        color: black;
	    }
````


>caption 

![Apply Css Class Tool Pic](images/ApplyCssClassToolPic.png)

## Using ContentAreaCssFile property

The example shows how to set a default background of the content area:

Setting the property from the markup

````XML
	    <telerik:radeditor id="RadEditor1" runat="server" ContentAreaCssFile="~/ContentAreaCssFile.css">
	    </telerik:radeditor>
````



Setting the property from the Code-behind

>tabbedCode

````C#
	        RadEditor1.ContentAreaCssFile = "~/ContentAreaCssFile.css";
````



````VB
	        RadEditor1.ContentAreaCssFile = "~/ContentAreaCssFile.css"
````


>end

Setting the CSS rules

````XML
	    body
	    {
	        background-color: red;
	        color: white;
	    }
````



Note that the __RadEditor__ control has some default styling for some of the elements inside the content area,so that the user could easily interact with them in the __Design__ mode. Using the __ContentAreaCssFile__ property for custom stylization willoverride the default one. Example for an element with such stylization is the __table__.

In addition to preserve or override this default stylization and preserve the user-friendly interface you could follow this[online live demo project](http://demos.telerik.com/aspnet-ajax/editor/examples/settingcontentareadefaults/defaultcs.aspx#qsf-demo-source)for the whole CSS file or use these example CSS rules:

````XML
	    body 
	    {
		padding:3px;
		background-image: none;
		margin: 0;
		text-align: left;
		word-wrap: break-word;
	    }
	
	    form 
	    {
		    background-color:#efefef;
		    border: 1px dashed #555;
	    }
	
	    table 
	    {
		    border-right: 1px dashed #999;
		    border-bottom: 1px dashed #999;
	    }
	
	    table td 
	    {
		    padding: 1px;
		    border-top: 1px dashed #999;
		    border-left: 1px dashed #999;
	    }
	
	    table th 
	    {
		    padding: 1px;
		    border-top: 1px dashed #000;
		    border-left: 1px dashed #000;
	    }
````



## Using CSSFiles property

The example shows how to populate the __Apply CSS class__ dropdown and define the CSS rules for the corresponding options.

Setting the property from the markup

````XML
	    <telerik:radeditor runat="server" id="RadEditor1" >
	        <CssFiles>
	            <telerik:EditorCssFile Value="~/ContentAreaCssFile.css" />
	        </CssFiles>
	    </telerik:radeditor>
````



Setting the property from the Code-behind

>tabbedCode

````C#
	        RadEditor1.CssFiles.Add("~/ContentAreaCssFile.css");
````



````VB
	        RadEditor1.CssFiles.Add("~/ContentAreaCssFile.css")
````


>end

Setting the CSS rules

````XML
	    .redText 
	    {
	        color:red;
	    }
	
	    .greenText 
	    {
	        color:green;
	    }
````



Result:
>caption 

![Populated Tool Bar From Selectors](images/PopulatedToolBarFromSelectors.png)

>note Note that using a link to a CSS file in the head element, with global CSS selectors will affect the content of the RadEditor control as well.sing the __CssFiles__ property will override the CSS rules from these files. Also using an empty property will clear them.
>


The names populated in the dropdown menu could be modified from the property __CSSClasses__ with the attributes __Name__ and __Value__.__Name__ holds the value to the text which appears in the dropdown menu and __Value__ – the class name for the selected element.

Example:

Setting the property from the markup

````XML
	    <CssClasses>
	        <telerik:EditorCssClass Name="Red Text" Value=".redText" />
	        <telerik:EditorCssClass Name="Green Text" Value=".greenText" />
	    </CssClasses>
````



Setting the property from the Code-behind

>tabbedCode

````C#
	        EditorCssClass redText = new EditorCssClass("Red Text", ".redText");
	        EditorCssClass greenText = new EditorCssClass("Green Text", ".greenText");
	        RadEditor1.CssClasses.Add(redText);
	        RadEditor1.CssClasses.Add(greenText);
````



````VB
	        EditorCssClass redText = New EditorCssClass("Red Text", ".redText")
	        EditorCssClass greenText = New EditorCssClass("Green Text", ".greenText")
	        RadEditor1.CssClasses.Add(redText)
	        RadEditor1.CssClasses.Add(greenText)
````


>end

Result:
>caption 

![Populated Tool Bar From Css Classes](images/PopulatedToolBarFromCssClasses.png)

>note Class name (Value) set within the __CSSClasses__ property, which does not exist as selector in one of the CSS files will not be populated in the menu. The opposite - if there is a class name not set within the __CSSClasses__ , but exists in a CSS file will be restricted also.
>


## User functionality for previewing the content without custom stylization

The built-in tool __Show/Hide Borders__ gives the possibility to the users to preview the content without the set default customization.This is due to the reason that after sending, submitting or sending the content outside the scope of the Editor’s iframe the stylization is not included and does notdepend on the CSS files pointed from the properties. This tool (button) actually disables the CSS links in the head element of the iframe.

The followin example shows the functionality with this custom CSS rules:

````XML
	    body 
	    {
	    background-color:rgba(155, 119, 119, 0.58);
	    color: white;
	    }
	
	    table 
	    {
	        border:1px solid black;
	        color: red;
	    }
	
	    table td 
	    {
	        border:1px solid black;
	    }
````



Result:

With the tool turned ON:
>caption 

![Borders ButtonON](images/BordersButtonON.png)

With the tool turned OFF:
>caption 

![Borders ButtonOFF](images/BordersButtonOFF.png)

# See Also

 * [Default Font for Editable Content]({%slug editor/managing-content/content-area-appearance/default-font-for-editable-content%})

 * [Set Editor Background and Color]({%slug editor/managing-content/content-area-appearance/set-editor-background-and-color%})

 * [Set Defaults]({%slug editor/managing-content/content-area-appearance/set-defaults%})

 * [Content Area Appearance Problems]({%slug editor/troubleshooting/content-area-appearance-problems%})