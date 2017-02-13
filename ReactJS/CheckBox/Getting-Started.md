---
layout: post
title: Getting-started
description: Getting started for CheckBox
platform: ReactJS
control: CheckBox
documentation: ug
---

# GettingStarted

This section discloses the details on how to render and configure **CheckBox** component in a **ReactJS** application.

## Create a CheckBox

Create an HTML page and refer the neccessary script and CSS dependency files in your application with the help of given [getting started documention](http://help.syncfusion.com/reactjs)

With ReactJS, the components can be initialized in two ways. 

1. Using jsx Template
2. Without using jsx Template

### Using jsx Template

You can render EJ components by using JSX template, wherein this JSX file will be converted to its equivalent JS file. 

* Create an HTML page and render a <div> element with an ID set to it.

{% highlight html %}

<body>
    <div id="dtp"></div>
</body>

{% endhighlight %}

2. Create a JSX file for rendering Checkbox component using <EJ.Checkbox> syntax. Add required properties to it in <EJ.Checkbox> tag element

{% highlight html %}

    ReactDOM.render(
    <div>
        <br />
        Category
        <br />
        <br />
        <table>
            <tr>
                <td>
                    <EJ.CheckBox id="music" text="Music" name="music" value="music" checked={true}></EJ.CheckBox>
                </td>
                <td>
                    <EJ.CheckBox id="sports" text="Sports" name="sports" value="sports" enableTriState={true} checkState="indeterminate"></EJ.CheckBox>
                </td>
                <td>
                    <EJ.CheckBox id="bike" text="Bike riding" name="bike" value="bike"></EJ.CheckBox>
                </td>
            </tr>
        </table>
        <br />
        <br />
        Favourite search engines
        <br />
        <br />
        <table>
            <tr>
                <td>
                    <EJ.CheckBox id="google" text="Google" name="google" value="google" checked={true}></EJ.CheckBox>
                </td>
                <td colspan="2">
                    <EJ.CheckBox id="yahoo" text="yahoo" name="yahoo" value="yahoo" enableTriState={true} checkState="indeterminate"></EJ.CheckBox>
                </td>
                <td colspan="2">
                    <EJ.CheckBox id="bing" text="Bing" name="bing" value="bing"></EJ.CheckBox>
                    </twd>
            </tr>
        </table>
    </div>,
    document.getElementById('dtp')
    );    

{% endhighlight %}

3. Define an HTML element for adding Checkbox in the application and refer the JSX file created.

 {% highlight html %}

<body>
    <div id="dtp"></div>

    <!-- CheckBox.jsx created in previous step-->
    <script type="text/babel" src="CheckBox.jsx">
    </script>   
</body>

{% endhighlight %}

Now the jsx file will be compiled into its equivalent Javascript file by means of Babel. 

Execute the above code to render CheckBox component. 

![](Getting-Started_images/Checkbox_jsx.png)

### Without using jsx Template

The CheckBox component can be initialized without using JSX template. 

1. Create an HTML page and render a <div> element with an ID set to it. 

{% highlight HTML %}
Hobbies
<table>
    <tr>
        <td>
            <div id="check1"></div>
        </td>
        <td>
            <div id="check2"></div>
        </td>
    </tr>
</table>

{% endhighlight %}

2. Render the CheckBox component by using the below mentioned code snippet.

{% highlight javascript %}

ReactDOM.render(
    React.createElement(EJ.CheckBox, {
        id: "check_btn1",
        name: "music",
        value: "music",
        text: "Music",
        checked: true
    }),
document.getElementById('check1')
);

ReactDOM.render(
    React.createElement(EJ.CheckBox, {
        id: "check_btn2",
        name: "sports",
        value: "sports",
        text: "Sports"
    }),
document.getElementById('check2')
);

{% endhighlight %}

Run the above code snippet to get the following output.

![](getting-started_images/Checkbox.png) 
