---
layout: post
title: Getting-started
description: Getting started for DateTimePicker
platform: ReactJS
control: DateTimePicker
documentation: ug
---

# GettingStarted

This section discloses the details on how to render and configure DateTimePicker component in a ReactJS application.

## Create a DateTimePicker

Create an HTML page and refer the neccessary script and CSS dependency files in your application with the help of given [getting started documention](http://help.syncfusion.com/reactjs).

With ReactJS, the components can be initialized in two ways. 

1. Using jsx Template
2. Without using jsx Template

### Using jsx Template

You can render EJ components by using JSX template, wherein this JSX file will be converted to its equivalent JS file. 

1. Create a div element in the HTML file and give it an ID. 

{% highlight html %}

    <body>
        <div id="dtp"></div>
    </body>

{% endhighlight %}

2. Create a JSX file and initialize DateTimepicker component by using the below code snippet.

{% highlight html %}

    ReactDOM.render(   
        <EJ.DateTimePicker id="dtp" value={new Date()}>
        </EJ.DateTimePicker>,
        document.getElementById('dtp')
    );

{% endhighlight %}

3. Refer the JSX file created in last step in the HTML file as given below. 

 {% highlight html %}

        <body>
            <div id="dtp"></div>

            <!-- Datetimepicker.jsx created in previous step-->
            <script type="text/babel" src="Datetimepicker.jsx">
            </script>   
        </body>

{% endhighlight %}

Now the jsx file will be compiled into its equivalent Javascript file by means of Babel. 

Execute the above code to render Datetimepicker component. 

![](Getting-Started_images/datetime.png)

### Configuring DateTimePicker

#### Set minDateTime and maxDateTime

EJ DateTimePicker provides API through which you can set the maximum and minimum allowed date and time values. Min and Max date and time values can be set at initialization as show below.

{% highlight javascript %}

    ReactDOM.render(   
        <EJ.DateTimePicker id="dtp" minDateTime={new Date("11/1/2016 10:00 AM")} maxDateTime={new Date("11/27/2016 10:00 PM")}>
        </EJ.DateTimePicker>,
        document.getElementById('dtp')
    );

{% endhighlight %}

The following screenshot illustrates the output of above code.

![](getting-started_images/minmax.png) 

>_Note:_ _You need to refer **browser.min.js** file in the script section and specify the type attribute of script tag to **text/babel** for compiling the JSX template._

> _Note:_ _You can find the DateTimePicker properties from the_ [API reference](https://help.syncfusion.com/api/js/ejdatetimepicker) _document._

### Without using jsx Template

The DateTimepicker component can be initialized without using JSX template. 

1. Create an HTML page and render a <div> element with an ID set to it. 

{% highlight HTML %}

    <div id="dtp"></div>

{% endhighlight %}

2. Render the DateTimePicker component by using the below mentioned code snippet.

{% highlight javascript %}

    ReactDOM.render(
                React.createElement(EJ.DateTimePicker, {
                    id: "dtp-0",
                    value: new Date()
                }
            ),
            document.getElementById('dtp')

{% endhighlight %}

Run the above code snippet to get the following output.

### Configuring DateTimePicker

#### Set minDateTime and maxDateTime

EJ DateTimePicker provides API through which you can set the maximum and minimum allowed date and time values. Min and Max date and time values can be set at initialization as show below.

{% highlight javascript %}

    ReactDOM.render(
                React.createElement(EJ.DateTimePicker, {
                    id: "dtp-0",
                    minDateTime: new Date("11/1/2016 10:00 AM"),
                    maxDateTime: new Date("11/27/2016 10:00 PM")
                }
            ),
            document.getElementById('dtp')
            );

{% endhighlight %}

The following screenshot illustrates the output of above code.

![](getting-started_images/minmax.png) 
