---
layout: post
title: Render Chart in multiple layouts in ReactJS Chart | Syncfusion
description: Learn here all about Multiple panes support in syncfusion ReactJS Chart control,its element and more.                   
platform: ReactJS
control: Chart
documentation: ug
api : /api/js/ejchart
---

# Multiple panes in ReactJS Chart

Chart area can be divided into multiple panes using the [`rowDefinitions`](../api/ejchart.html#members:rowdefinitions) and [`columnDefinitions`](../api/ejchart.html#members:rowdefinitions) properties.

### Row Definitions

To split the chart area vertically into a number of rows, use [`rowDefinitions`](../api/ejchart.html#members:rowdefinitions) of the chart. 

* You can allocate space for each row by using the [`unit`](../api/ejchart.html#members:rowdefinitions-unit) option that determines whether the chart area should be split by *percentage* or *pixels* for the given [`rowHeight`](../api/ejchart.html#members:rowdefinitions-rowheight) value of the rowDefinitions.
 
* To associate a vertical axis to a row, specify the rowDefinitions **index** value to the [`rowIndex`](../api/ejchart.html#members:primaryyaxis-rowindex) property of the chart axis.

* To customize each row’s horizontal line, use [`lineColor`](../api/ejchart.html#members:rowdefinitions-linecolor) and [`lineWidth`](../api/ejchart.html#members:rowdefinitions-linewidth) property.


{% highlight javascript %}

"use strict";
var rowDefinitions=[{
            //  Split first row of the chart area
            unit : 'percentage',                 
            lineColor : 'Gray',
            rowHeight : 50,
            linewidth : 0
            }, {
            //  Split second row of the chart area
            unit : 'percentage',                 
            lineColor : 'green',
            rowHeight : 50,
            linewidth : 0
}]

var axes=[{
            //Create secondary axis and bind it to second row of chart area
            name: "yAxis1",
            rowIndex: 1
}]

var series=[{
            //Binding vertical axis name
            yAxisName: "yAxis1",
            // ...
}]

ReactDOM.render(
    <EJ.Chart id="default_chart_sample_0"
	rowDefinitions={rowDefinitions}
	axes={axes}
	series={series}
    >        
            
    </EJ.Chart>,
		  document.getElementById('chart')
);


{% endhighlight %}

![Multiple Panes in ReactJS Chart](Multiple-Panes_images/Multiple-Panes_img1.png)


[Click](http://js.syncfusion.com/demos/web/#!/azure/chart/chartaxes/multipleaxes) here to view the online demo sample for multiple panes.


**Row Span**

For spanning the vertical axis along multiple panes vertically, you can use [`rowSpan`](../api/ejchart.html#members:primaryyaxis-rowspan) property of axis. 

{% highlight javascript %}

"use strict";
var rowDefinitions=[{

                         // ...
                  },{

                         // ...
}]

var axes=[{

                          // ...
}]
		
var primaryYAxis={
                    //  Span the PrimaryYAxis                    
                    rowSpan : 2,
}

var series=[{
		// ...
}]

ReactDOM.render(
    <EJ.Chart id="default_chart_sample_0"
	rowDefinitions={rowDefinitions}
	axes={axes}
	series={series}
    primaryYAxis={primaryYAxis}
    >        
            
    </EJ.Chart>,
		  document.getElementById('chart')
);


{% endhighlight %}

![Row Span in ReactJS Chart](Multiple-Panes_images/Multiple-Panes_img2.png)

## Column Definitions

To split the chart area horizontally into a number of columns, use [`columnDefinitions`](../api/ejchart.html#members:columndefinitions) of the chart.

* You can allocate space for each column by using the [`unit`](../api/ejchart.html#members:columndefinitions-unit) option that determines whether the chart area should be split by *percentage* or *pixels* for the given [`columnWidth`](../api/ejchart.html#members:columndefinitions-columnwidth) value of the columnDefinitions.
 
* To associate a horizontal axis to a column, specify the columnDefinitions **index** value to the [`columnIndex`](../api/ejchart.html#members:primaryxaxis-columnindex) property of the chart axis.
 
{% highlight javascript %}

"use strict";
var columnDefinitions= [{
                //  Split first column of the chart area
                    unit : 'percentage', 
                    columnWidth : 50,
                }, {
                    //  Split second column of the chart area
                    unit : 'percentage',                 
                    columnWidth : 50,
                }]		

var axes=[{
			//Create secondary axis and bind it to second column of chart area 
            name: "xAxis1",
            columnIndex: 1
            // ...
        }]
		
var series=[{
            //Binding horizontal axis name
            xAxisName: "xAxis1",
            // ...
}]

ReactDOM.render(
    <EJ.Chart id="default_chart_sample_0"
	columnDefinitions={columnDefinitions}
	axes={axes}
	series={series}
    >        
            
    </EJ.Chart>,
		  document.getElementById('chart')
);


{% endhighlight %}

![Column Definition in ReactJS Chart](Multiple-Panes_images/Multiple-Panes_img3.png)


**Column Span**

For spanning the horizontal axis along multiple panes horizontally, you can use [`columnSpan`](../api/ejchart.html#members:primaryxaxis-columnspan) property of axis. 

{% highlight javascript %}

"use strict";
var columnDefinitions= [{
                      // ...
                  },{
                      // ...
}]	

var axes=[{
              // ...
         }]
		
var series=[{
              // ...
           }]
		   
var primaryXAxis= {
              //  Span the PrimaryXAxis                    
              columnSpan : 2,
}

ReactDOM.render(
    <EJ.Chart id="default_chart_sample_0"
    primaryXAxis={primaryXAxis}
	columnDefinitions={columnDefinitions}
	axes={axes}
	series={series}
    >        
            
    </EJ.Chart>,
		  document.getElementById('chart')
);


{% endhighlight %}

![Column Span in ReactJS Chart](Multiple-Panes_images/Multiple-Panes_img4.png)
