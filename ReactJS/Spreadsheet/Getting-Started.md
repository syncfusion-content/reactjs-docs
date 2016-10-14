---
title: Getting Started for React JS Spreadsheet
description: How to create a Spreadsheet with data source, apply format and export it as excel file.
platform: React JS
control: Spreadsheet
documentation: Ug
keywords: 
---

# Getting started

This section explains you the steps required to populate the Spreadsheet with data, format, and export it as excel file. This section covers only the minimal features that you need to know to get started with the Spreadsheet.

## Adding Script Reference

Create an **HTML** page and add the scripts references in the order mentioned in the following code example.

{% highlight html %}

<!DOCTYPE html>
<html>
    <head>
        <!-- Essential Studio for JavaScript  theme reference -->
        <link rel="stylesheet" href="http://cdn.syncfusion.com/14.3.0.49/js/web/bootstrap-theme/ej.web.all.min.css" />           
        <!--  react script  -->
        <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react-dom.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js"></script>
        <!--  jquery script  -->
        <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"></script>
        <script src="http://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js"></script>
        <!--  jsrender script  -->
        <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
        <!-- Essential JS UI widget -->    
        <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js"></script>
        <script src="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.web.react.min.js"></script>

        <!--Add custom scripts here -->
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use [CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

**Note:**

* For details about Spreadsheet internal and external dependencies refer following [`link`](http://help.syncfusion.com/js/spreadsheet/dependencies "link")
* `react.js` and `react-dom.js` are the core files needed to create react elements.
* `browser.min.js` file is required for code transform.
* `ej.web.react.min.js`  is a react-syncfusion bridge to render Syncfusion components.

## Initialize Spreadsheet

Add a `div` container to render the Spreadsheet.

{% highlight html %}

<!DOCTYPE html>
<html>    
    <body>
        <div id="Spreadsheet"></div>
    </body>
</html>

{% endhighlight %}

Initialize the Spreadsheet by using the `EJ.Spreadsheet` tag. The Spreadsheet is rendered based on default `width` and `height`. You can also customize the Spreadsheet dimension by setting the `width` and `height` attribute in `scrollSettings`.

{% highlight html %}

<!DOCTYPE html>
<html>    
    <body>
        <div id="Spreadsheet"></div>
        <script type="text/babel">
             ReactDOM.render(
                   <EJ.Spreadsheet></EJ.Spreadsheet>,
                   document.getElementById('Spreadsheet')
        );  
        </script>
    </body>
</html>

{% endhighlight %}

Now, the Spreadsheet is rendered with default row and column count.

![](Getting-Started_images/Getting-Started_img1.png)

## Populate Spreadsheet with data

Now, this section explains how to populate JSON data to the Spreadsheet. You can set `dataSource` attribute in `sheet` settings to populate JSON data in 
Spreadsheet.

{% highlight html %}

<script type="text/babel">
               var sheets = [
                     // the datasource "window.defaultData" is referred from 'http://js.syncfusion.com/demos/web/scripts/xljsondata.js'
                     { rangeSettings: [{ dataSource: window.defaultData }] }
                          ];
               $(function(){
                 ReactDOM.render(
                 <EJ.Spreadsheet sheets={sheets}></EJ.Spreadsheet>,
                 document.getElementById('Spreadsheet')
                 );
                 });
</script>

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img2.png)

## Apply Conditional Formatting

Conditional formatting helps you to apply formats to a cell or range with certain colour based on the cells values. You can use `allowConditionalFormats` attribute to enable/disable Conditional formats.
To apply conditional formats for a range use `cFormatRule` attribute . The following code example illustrates this behaviour,

{% highlight html %}

<script type="text/babel">
        var sheets = [
        { 
        rangeSettings: [{ dataSource: window.defaultData }],
        cFormatRule:[{ action: ej.Spreadsheet.CFormatRule.GreaterThan, inputs: ["10"], color: ej.Spreadsheet.CFormatHighlightColor.RedFill, range: "D2:D8" }]
        },
        ];

        $(function(){

        ReactDOM.render(
        <EJ.Spreadsheet sheets={sheets}></EJ.Spreadsheet>,
        document.getElementById('Spreadsheet')
        );

        });

</script>

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img3.png)

## Export Spreadsheet as Excel File

The Spreadsheet can save its data, style, format into an excel file. To enable save option in Spreadsheet set `allowExporting` option in `exportSettings` as `true`. Since Spreadsheet uses server side helper to save documents set `excelUrl` in `exportSettings` option. The following code example illustrates this behaviour,


{% highlight html %}

<script type="text/babel">
        var exportSettings = {
        excelUrl:"http://js.syncfusion.com/demos/ejservices/api/JSXLExport/ExportToExcel"
        };
        $(function(){

        ReactDOM.render(
        <EJ.Spreadsheet exportSettings={exportSettings} ></EJ.Spreadsheet>,
        document.getElementById('Spreadsheet')
        );

        });

</script>});

{% endhighlight %}

Use shortcut `Ctrl + S` to save Spreadsheet as excel file.
