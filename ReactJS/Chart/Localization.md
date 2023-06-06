---
layout: post
title: Localization in ReactJS Chart Control | Syncfusion
description: Learn hera about Localization support in Syncfusion Essential ReactJS Chart Control, its elements, and more.
platform: ReactJS
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Localization in ReactJS Chart

EjChart supports localization for its axis labels and tooltip. To render the chart with specific culture you have to refer the corresponding **globalize** culture script and need to specify the culture name in [`locale`](../api/ejchart#members:locale) property of chart.   

{% highlight html %}


<head> 
<!--Refer french globalize culture script-->
<script src="../scripts/cultures/globalize.culture.fr-FR.min.js"></script>
</head>

<body>
    <div id="chartcontainer"></div>
</body>

{% endhighlight %}

{% highlight javascript %}

"use strict";
	ReactDOM.render(
		<EJ.Chart id="default_chart_sample_0"
		//Render chart in french locale
        locale= {'fr-FR'}
		>        
            
		</EJ.Chart>,
			document.getElementById('chart')
	);


{% endhighlight %}

![ReactJS Chart Localization](Localization_images/Localization_img1.png)

[Click](https://ej2.syncfusion.com/home/#!/azure/chart/chartcustomization/localization) here to view the localization chart online demo sample.


