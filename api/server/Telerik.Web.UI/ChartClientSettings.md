---
title: Telerik.Web.UI.ChartClientSettings
page_title: Telerik.Web.UI.ChartClientSettings
description: Telerik.Web.UI.ChartClientSettings
---

# Telerik.Web.UI.ChartClientSettings

Chart client settings

## Inheritance Hierarchy

* System.Object
* Telerik.Charting.StateManagedObject
* Telerik.Web.UI.ChartClientSettings

## Properties

###  EnableAxisMarkers `Boolean`

Gets or sets a value indicating whether the zoom assist axis markers are enabled.

###  AxisMarkersColor `Color`

Gets or sets a value indicating the color of the zoom assist axis markers.

###  AxisMarkersSize `Int32`

Gets or sets a value indicating the size of the axis markers in pixels (size for the YAxis marker represents its width, while size for the XAxis marker -- its height).

###  EnableZoom `Boolean`

Gets or sets a value indicating whether the client-side zoom functionality is enabled.

###  ZoomRectangleColor `Color`

Gets or sets a value indicating the color of the zoom rectangle.

###  ZoomRectangleOpacity `Single`

Gets or sets a value indicating the opacity of the zoom rectangle.

###  ScrollMode `ChartClientScrollMode`

Gets or sets a value indicating the plotarea client scroll mode.

###  YScrollOffset `Single`

Gets or sets a value indicating the YAxis scroll offset ratio.

###  XScrollOffset `Single`

Gets or sets a value indicating the XAxis scroll offset ratio.

###  YScale `Single`

Gets or sets a value indicating the plotarea scale value by Y axis.

###  XScale `Single`

Gets or sets a value indicating the plotarea scale value by X axis.

###  ViewStateIgnoresCase `Boolean`

Gets if view sate should ignore case

###  ViewState `StateBag`

Sate bag to store view state content

## Methods

###  ToString

#### Returns

`System.String` 

###  Telerik.Charting.IChartingStateManager.LoadViewState

Loads data from a view state

#### Parameters

#### state `System.Object`

View state to load data from

#### Returns

`System.Void` 

###  Telerik.Charting.IChartingStateManager.SaveViewState

Saves object data to a view state

#### Returns

`System.Object` Saved view state object

###  Telerik.Charting.IChartingStateManager.TrackViewState

Tracks view state changes

#### Returns

`System.Void` 

###  CloneState

Makes a view state clone

#### Returns

`System.Web.UI.StateBag` StateBag

###  SaveViewState

Saves object data to a view state

#### Returns

`System.Object` Saved view state object

###  TrackViewState

Tracks view state changes

#### Returns

`System.Void` 

###  LoadViewState

Loads data from a view state

#### Parameters

#### state `System.Object`

View state to load data from

#### Returns

`System.Void` 

###  SetDirty

Sets the item dirty state

#### Returns

`System.Void` 

###  ToString

ToString() override. Used in the properties grid to avoid object type showing.

#### Returns

`System.String` Empty string

