---
id: dxPieChartSeriesTypes.CommonPieChartSeries.smallValuesGrouping.mode
type: Enums.SmallValuesGroupingMode
default: 'none'
---
---
##### shortDescription
Specifies the segment grouping mode.

---
If you need to group specific chart segments into one, set the properties of the **smallValuesGrouping** configuration object. Using the **mode** property of this object, you can define the grouping mode.

Use a *'topN'* mode to group all segments with an index that is equal to or greater than the value of the **topCount** property.

To group all segments with a value less than the value of the **threshold** property, set a *'smallValueThreshold'* mode.

To switch the grouping off, assign *'none'* to the **mode** property.

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/Charts/DoughnutWithTopNSeries/"
}