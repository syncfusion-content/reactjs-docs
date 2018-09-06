---
layout: post
title: Getting Started with Syncfusion Web Report Designer
description: How to start with Syncfusion Web Report Designer
platform: React JS
control: ReportDesigner
documentation: ug
---

# Getting Started

This section explains briefly about how to create a ReportDesigner in React JS.

## Script and CSS Reference

Create a **HTML** page and add the script and CSS references in the <head> tag of the html page.

{% highlight html %}

<!DOCTYPE html>
<html>
    <head>
        <!-- theme reference -->
        <link rel="stylesheet" href="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/bootstrap-theme/ej.web.all.min.css" />
        <link rel="stylesheet" href="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/bootstrap-theme/ej.reportdesigner.min.css" />  
        <link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.css" rel="stylesheet" />
        <link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.css" rel="stylesheet" />
        <!--  react script  -->
        <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react-dom.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js"></script>
        <!--  jquery script  -->
        <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/jsrender/0.9.90/jsrender.min.js" type="text/javascript"></script>
        <!--  code miror script  -->
        <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.js" type="text/javascript"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.js" type="text/javascript"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/sql-hint.min.js" type="text/javascript"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/mode/sql/sql.min.js" type="text/javascript"></script>
        <!-- Essential JS UI widget -->    
        <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/ej.web.all.min.js"></script>
        <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/ej.reportdesigner.min.js"></script>
        <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/common/ej.web.react.min.js"></script>
        <!--Add custom scripts here -->
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

N> In the above code, `ej.web.all.min.js` script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use [CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

* `react.js` and `react-dom.js` are the core files needed to create react elements.
* `browser.min.js` file is required for code transform.
* `ej.web.react.min.js`  is a react-syncfusion bridge to render Syncfusion components.

## Initialize and configure the control

Control can be initialized in two ways.

 * Using jsx Template
 * Without using jsx Template
 
### Using jsx Template

While making use of jsx template, we have to create both the html and jsx files. The `.jsx` file should be converted into `.js` file using [gulp](/reactjs/overview#converting-jsx-to-javascript-with-react) command and then needs to be added as a reference in the html page.
 
#### Control Initialization

Add a `div` container to render the ReportDesigner.

{% highlight html %}

<!DOCTYPE html>
<html>    
     <body>
         <div id="reportDesigner"></div>
         <script src="scripts/default.js"></script>
     </body>
</html>

{% endhighlight %}

Initialize the ReportDesigner by using the `EjReportDesigner` tag.

{% highlight html %}

"use strict";
ReactDOM.render(  
    <EJ.ReportDesigner
		id = "designerId"
		serviceUrl = {'http://js.syncfusion.com/ejservices/api/ReportDesigner'}
	</EJ.ReportDesigner>,
	document.getElementById('reportDesigner')
);

{% endhighlight %}

N> The above jsx template needs to be converted from `.jsx` to `.js` extension by using `gulp` nuget package (refer [here](/reactjs/overview#converting-jsx-to-javascript-with-react)) and then it must be referred in the html page.

#### Run the Application

Run the sample application and you can see the ReportDesigner on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started-img1.png) 

### Using without jsx Template

ReportDesigner can be created from a HTML `DIV` element with the HTML `id` attribute set to it. Refer to the following code example.

{% highlight html %}

<body>
	<div id="reportdesigner"></div>
</body>

{% endhighlight %}

Initialize the ReportDesigner control by adding the following script code to the body section of the HTML document.

{% highlight html %}

<script type="text/javascript">
    ReactDOM.render(
    React.createElement(EJ.ReportDesigner, {
        id: "designerId",
        serviceUrl: 'http://js.syncfusion.com/ejservices/api/ReportDesigner'
    }),
    document.getElementById('reportdesigner')
);
</script>

{% endhighlight %}

Run the application and you can see the ReportDesigner on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started-img1.png) 
