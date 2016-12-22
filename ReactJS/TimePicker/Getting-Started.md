---
layout: post
title: getting-started
description: getting started for TimePicker
platform: reactjs
control: TimePicker
documentation: ug
---

# Getting Started

This section explains you how to render and configure TimePicker component in a ReactJS application.

## Adding Scripts and Style references

Create an HTML page and refer the necessary script and CSS dependency files in your application with the help of given  [React Getting Started Documentation.](https://help.syncfusion.com/reactjs/overview)

Example

{% highlight html %}
<!DOCTYPE html>
   <html>
     <head>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta name="description" content="Essential Studio for React JS">
        <meta name="author" content="Syncfusion">
        <title>Getting Started for TimePicker React JS</title>
        <!-- Essential Studio for JavaScript  theme reference -->
        <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <!-- Essential Studio for JavaScript  script references -->
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
         <script src="http://cdn.syncfusion.com/js/assets/external/react.min.js"></script>
        <script src="http://cdn.syncfusion.com/js/assets/external/react-dom.min.js"></script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.web.react.min.js"></script>
        <!-- Add your custom scripts here -->
    </head>
        <body>
        </body>
   </html>

{% endhighlight %}

## Configure Properties

### Value

 This property specifies the list of time range to be disabled in TimePicker control.To know more about TimePicker properties please refer the [API reference](https://help.syncfusion.com/api/js/ejtimepicker)

{% highlight html %}

ReactDOM.render(   
		  <EJ.TimePicker id="timepicker" value={"10:30 PM"} >
</EJ.TimePicker>,
document.getElementById('dtp')
);

{% endhighlight %}

### DisableTimeRanges

 This property specifies the list of time range to be disabled in TimePicker control.To know more about TimePicker properties please refer the [API reference](https://help.syncfusion.com/api/js/ejtimepicker)

{% highlight html %}

var  disableTime= [{ startTime: "3:00 AM", endTime: "6:00 AM" },
                    { startTime: "1:00 PM", endTime: "3:00 PM" },
                    { startTime: "8:00 PM", endTime: "10:00 PM" }];

ReactDOM.render(   
		  <EJ.TimePicker id="timepicker"  disableTimeRanges={disableTime} >
</EJ.TimePicker>,
document.getElementById('dtp')
);

{% endhighlight %}


In the JSX, need to declare the Timepicker properties. Refer to the following code.,

{% highlight html %}

ReactDOM.render(   
        <EJ.TimePicker value={20} >
        </EJ.TimePicker>,
        document.getElementById('timepicker')
    );

{% endhighlight %}

With ReactJS, components can be initialized in two ways. 

1. Using jsx Template
2. Without using jsx Template



### Using jsx Template

You can render EJ component by using JSX template, wherein the document will be converted to its equivalent JS file. 

1. Create an input element with an ID in the HTML file. 

{% highlight html %}

<body>
    <div id="timepicker"></div>
</body>

{% endhighlight %}

2. Create a JSX file and render Timepicker component by using the below code snippet.

{% highlight html %}

    ReactDOM.render(   
        <EJ.TimePicker id="timepicker">
        </EJ.TimePicker>,
        document.getElementById('timepicker')
    );

{% endhighlight %}

3. Refer the JSX file created in last step in the HTML file as given below. 

 {% highlight html %}

<body>
    <div id="timepicker"></div>

    <!-- timepicker.jsx created in previous step-->
    <script type="text/babel" src="timepicker.jsx">
    </script>   
</body>

{% endhighlight %}

Now the jsx file will be compiles into its equivalent JavaScript file by means of Babel. 

### Without using jsx Template

The Timepicker can be created from a HTML `INPUT` element with the HTML `id` attribute set to it. Refer to the following code example.

{% highlight html %}

<body>
    <input id="timepicker"/>
</body>

           
{% endhighlight %}

{% highlight javascript %}

 <script>

 ReactDOM.render(
    React.createElement(EJ.Chart, {id: "timepicker"}       
    ),
	document.getElementById('timepicker')
);      

 </script>

 {% endhighlight %}

Execute the above code to render Timepicker component. 

![](Getting-Started_images/timepicker.png)

> _Note:_ _You can find the TimePicker properties from the_ [API reference](https://help.syncfusion.com/api/js/ejtimepicker) _document._
