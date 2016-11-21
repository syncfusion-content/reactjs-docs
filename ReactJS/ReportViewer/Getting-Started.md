---
layout: post
title: Getting Started
description: getting started
platform: React JS
control: ReportViewer
documentation: ug
---

# Getting Started

This section explains briefly about how to create a ReportViewer in React JS.

## Script and CSS Reference

Create a **HTML** page and add the script and CSS references in the order mentioned in the following code example.

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
        <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
        <!-- Essential JS UI widget -->    
        <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js"></script>
        <script src="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.web.react.min.js"></script>

        <!--Add custom scripts here -->
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

In the above code, `ej.web.all.min.js` script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use [CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

**Note:**

* `react.js` and `react-dom.js` are the core files needed to create react elements.
* `browser.min.js` file is required for code transform.
* `ej.web.react.min.js`  is a react-syncfusion bridge to render Syncfusion components.

### Control Initialization

Add a `div` container to render the ReportViewer.

{% highlight html %}

<!DOCTYPE html>
<html>    
     <body>
         <div id="groupingAggregate"></div>
     </body>
</html>

{% endhighlight %}

Initialize the ReportViewer by using the ` EjReportViewer` tag.

{% highlight html %}

<!DOCTYPE html>
<html>
<head>
    <style>
        .e-reportviewer * {
            -webkit-box-sizing: content-box !important;
            -moz-box-sizing: content-box !important;
            box-sizing: content-box !important;
        }
    </style>
</head>
<body>        
        <div style="height: 650px; width: 1250px; min-height: 404px;" id="groupingAggregate"></div>   
    <script type="text/jsx">      
        EjReportViewer = React.createClass({

        render : function(){
        return (
        <div id={this.props.id}></div>
        );
        },
        componentDidMount : function(){

        $("#"+ this.props.id).ejReportViewer( {
                         reportServiceUrl: 'http://js.syncfusion.com/ejservices/api/RDLReport',
					     processingMode: ej.ReportViewer.ProcessingMode.Remote,
                         reportPath: 'GroupingAgg.rdl'
                    });
                },
            });

        React.render(
        <EjReportViewer id="container1" />, document.getElementById('groupingAggregate'));
    </script>    
</body>
</html>

{% endhighlight %}

N> Default RDL Report will be rendered, which is used in the online service. You can obtain sample rdl/rdlc files from Syncfusion installed location (%userprofile%\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\Common\Data\ejReportTemplate).

### Run the Application

Run the sample application and you can see the ReportViewer on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started_img1.png) 

ReportViewer with Grouping Aggregate Report
{:.caption}

## Load SSRS Server Reports

ReportViewer supports to load RDL/RDLC files from SSRS Server. The following steps help you to load reports from SSRS Server.

1. Set the `reportPath` from SSRS and SSRS `reportServerUrl` in the ReportViewer properties.

{% highlight html %}

<!DOCTYPE html>
<html>
<head>
    <style>
        .e-reportviewer * {
            -webkit-box-sizing: content-box !important;
            -moz-box-sizing: content-box !important;
            box-sizing: content-box !important;
        }
    </style>
</head>
<body>        
        <div style="height: 650px; width: 1250px; min-height: 404px;" id="territoryReportViewer"></div>   
    <script type="text/jsx">      
        EjReportViewer = React.createClass({

        render : function(){
        return (
        <div id={this.props.id}></div>
        );
        },
        componentDidMount : function(){

        $("#"+ this.props.id).ejReportViewer( {
                        reportServiceUrl: "http://ssrs.syncfusion.com/ReportingWebAPIService/api/SSRSReport",                        
                        processingMode: ej.ReportViewer.ProcessingMode.Remote,
                        reportPath: "/SSRSSamples2/Territory Sales new", 
                        reportServerUrl: "http://mvc.syncfusion.com/reportserver"                      
                    });
        },
        });

        React.render(
        <EjReportViewer id="container1" />, document.getElementById('territoryReportViewer'));
    </script>    
</body>
</html>

{% endhighlight %}

2. Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![](Getting-Started_images/Getting-Started_img2.png) 
   
   Report from SSRS
   {:.caption}

## Load RDLC Reports

The ReportViewer has data binding support to visualize the RDLC reports. The following code example helps you to bind data to ReportViewer.

1. Assign the RDLC report path to ReportViewer’s `reportPath` property and set the data sources to the ReportViewer’s `dataSources` property and specify the `processingMode` as local.

{% highlight html %}

<!DOCTYPE html>
<html>
<head>
    <style>
        .e-reportviewer * {
            -webkit-box-sizing: content-box !important;
            -moz-box-sizing: content-box !important;
            box-sizing: content-box !important;
        }
    </style>
</head>
<body>        
        <div style="height: 650px; width: 1250px; min-height: 404px;" id="areaCharts"></div>   
    <script type="text/jsx">      
        EjReportViewer = React.createClass({

        render : function(){
        return (
        <div id={this.props.id}></div>
        );
        },
        componentDidMount : function(){

        $("#"+ this.props.id).ejReportViewer( {
                       reportServiceUrl: 'http://js.syncfusion.com/ejservices/api/RDLCReport',
					   processingMode: ej.ReportViewer.ProcessingMode.Local,
                       reportPath: 'AreaCharts.rdlc',
                       dataSource: [{
                           value: [
							   { SalesPersonID: 281, FullName: 'Ito', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 0, Y2003: 28000, Y2004: 3018725 },
							   { SalesPersonID: 282, FullName: 'Saraiva', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 25000, Y2003: 14000, Y2004: 3189356 },
							   { SalesPersonID: 283, FullName: 'Cambell', Title: 'Sales Representative', SalesTerritory: 'North West', Y2002: 12000, Y2003: 13000, Y2004: 1930885 },
							   { SalesPersonID: 275, FullName: 'Blythe', Title: 'Sales Representative', SalesTerritory: 'North East', Y2002: 19000, Y2003: 47000, Y2004: 4557045 },
							   { SalesPersonID: 276, FullName: 'Mitchell', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 28000, Y2003: 46000, Y2004: 5240075 },
							   { SalesPersonID: 277, FullName: 'Carson', Title: 'Sales Representative', SalesTerritory: 'Central', Y2002: 33000, Y2003: 49000, Y2004: 3857163 },
							   { SalesPersonID: 278, FullName: 'Vargas', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 11000, Y2003: 14000, Y2004: 1764938 },
							   { SalesPersonID: 279, FullName: 'Reiter', Title: 'Sales Representative', SalesTerritory: 'South East', Y2002: 32000, Y2003: 26000, Y2004: 2811012 }
                            ],
                            name: 'AdventureWorksXMLDataSet'
                        }],
                    },
                });

        React.render(
        <EjReportViewer id="container1" />, document.getElementById('areaCharts'));
    </script>    
</body>
</html>

{% endhighlight %}

N> Default RDLC Report will be rendered, which is used in the online service.

2. Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![](Getting-Started_images/Getting-Started_img3.png) 
   
   Area Chart RDLC Report
   {:.caption}

