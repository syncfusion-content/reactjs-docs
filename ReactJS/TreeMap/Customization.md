---
layout: post
title: Customization
description: customization
platform: js
control: TreeMap
documentation: ug
---

# Customization

**TreeMap** control supports color customization to determine the exact combination of colors for tree nodes displayed in **TreeMap** and tooltip support to display additional information of treemap data.

## Color

You can customize the colors of the leaf nodes of **TreeMap** using the ColorMapping support of the **TreeMap**. 

ColorMapping is categorized into three different types such as,

* uniColorMapping
* rangeBrushColorMapping
* desaturationColorMapping

### Uni Color Mapping

You can color, all the leaf nodes with the same color by setting the `color` value of the `uniColorMapping` property of the **TreeMap**.

{% highlight js %}

"use strict";

var uniColorMapping = { color: "Crimson" };

ReactDOM.render(
    <EJ.TreeMap id="treemap1" uniColorMapping = {uniColorMapping}> </EJ.TreeMap>,
    document.getElementById('treemaps')
);



{% endhighlight %}



![](/js/TreeMap/Customization_images/Customization_img1.png)

### Range Color Mapping

You can group the leaf nodes based on the range of the data’s color values. You can set a unique color for every ranges. To achieve this, specify the `to` and `from` values as range bound and `color` value to fill the leaf nodes of the particular range, through the `rangeColorMapping` property of the **TreeMap**.

{% highlight js %}

"use strict";

var rangeColorMapping = [
                        { color: "#77D8D8", from: "0", to: "1" },
                        { color: "#AED960", from: "0", to: "2" },
                        { color: "#FFAF51", from: "0", to: "3" },
                        { color: "#F3D240", from: "0", to: "4" }
];
ReactDOM.render(
    <EJ.TreeMap id="treemap1" rangeColorMapping = {rangeColorMapping}></EJ.TreeMap>,
    document.getElementById('treemaps')
);



{% endhighlight %}



![](/js/TreeMap/Customization_images/Customization_img2.png)

### Desaturation Color Mapping

You can differentiate all the leaf nodes using the `desaturationColorMapping` property of the **TreeMap**. Differentiation is achieved, even though same color is applied for all the leaf nodes by varying the opacity of the leaf nodes based on the color value specified in the color value range using `rangeMinimum` and `rangeMaximum` value of the data collection. You can also bound the opacity range by setting `from` and `to` property of the `desaturationColorMapping`.

{% highlight js %}


"use strict";
var desaturationColorMapping = {
                        color: "DeepSkyBlue", from: "1", to: "0.2", rangeMinimum: "0",  
                        rangeMaximum: "4"                        
};
ReactDOM.render(
    <EJ.TreeMap id="treemap1" desaturationColorMapping = {desaturationColorMapping}></EJ.TreeMap>,
    document.getElementById('treemaps')
);





{% endhighlight %}



![](/js/TreeMap/Customization_images/Customization_img3.png)

## Tooltip

You can enable the tooltip support for the TreeMap by setting the `showTooltip` property to true. By default, it takes the property of the bound object that is referred to in the groupPath and displays its content when the corresponding node is tapped. The `tooltipTemplate` is a **HTML** element that is used to expose the custom template for the tooltip.

## Leaf Item Setting

You can customize the **Leaf level TreeMap items** using `leafItemSettings`. The Label and tooltip values take the property of bound object that is referred in the `labelPath` when defined.

{% highlight js %}
   
"use strict";
var leafItemSettings = { labelPath: "Region" };
ReactDOM.render(
    <EJ.TreeMap id="treemap1" leafItemSettings = {leafItemSettings} 
    showTooltip = {true}></EJ.TreeMap>,
    document.getElementById('treemaps')
);

   
{% endhighlight %}



![](/js/TreeMap/Customization_images/Customization_img4.png)

