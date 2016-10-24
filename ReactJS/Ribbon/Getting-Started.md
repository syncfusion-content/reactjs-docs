---
title: Getting Started for React JS Ribbon
description: Getting-Started
platform: React JS
control: Ribbon
documentation: Ug
keywords: 
---

# Getting Started

This section explains briefly how to create a `Ribbon`.

## Script & CSS Reference 

The Ribbon control has the following list of external JavaScript dependencies.

* [`jQuery`](http://jquery.com) 1.7.1 and later versions
* [`jsRender`](https://github.com/borismoore/jsrender) - to render the templates

The required ReactJS script dependencies as follows. And you can also refer [React](https://facebook.github.io/react/docs/getting-started.html) to know more about react js.

* `react.min.js` - [http://cdn.syncfusion.com/js/assets/external/react.min.js](http://cdn.syncfusion.com/js/assets/external/react.min.js)
* `react-dom.min.js` - [http://cdn.syncfusion.com/js/assets/external/react-dom.min.js](http://cdn.syncfusion.com/js/assets/external/react-dom.min.js)
* `ej.web.react.min.js` - [http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.web.react.min.js](http://cdn.syncfusion.com/14.3.0.49/js/common/ej.web.react.min.js)

{% highlight html %}

    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml">
    <head>
    <title>Ribbon Control</title>
    <!-- style sheet for default theme(flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!—jQuery dependency scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"></script>
    <!— ej script to render JavaScript control-->
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    </head>
    <body>
    </body>
    </html>

{% endhighlight %}

N> 1. In production, we highly recommend you to use our [`custom script generator`](http://help.syncfusion.com/js/custom-script-generator) to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [`GZip compression`](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en) in your server.
N> 2. For themes, you can use the `ej.web.all.min.css` CDN link from the code snippet given. To add the themes in your application, please refer to [`this link`](http://help.syncfusion.com/js/theming-in-essential-javascript-components).

## Control Initialization

Control can be initialized in two ways.

 * Using jsx Template
 * Without using jsx Template
 
## Using jsx Template

By using the jsx template, we can create the html file and jsx file. The `.jsx` file can be convert to `.js` file and it can be refered in html page.

Please refer to the code of HTML file.

{% highlight html %}

    <div id="ribbon-default"></div>
    <script src="app/ribbon/default.js"></script>
    <ul id="ribbonmenu1">
    <li><a>FILE</a>
       <ul>
         <li><a>New</a></li>
         <li><a>Open</a></li>
         <li><a>Save</a></li>
         <li><a>Save As</a></li>
         <li><a>Print</a></li>
	   </ul>
    </li>
    </ul>

{% endhighlight %}

Ribbon control can be initialized with the following in HTML document.

{% highlight html %}     
                
    ReactDOM.render(
    React.createElement(EJ.Ribbon, { width: "50%", "applicationTab-type": "menu", "applicationTab-menuItemID": "ribbonmenu1" }
    ),
    document.getElementById('ribbon-default')
    );

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img1.png)

N>  Set the required width to Ribbon, else default parent container or window width will be considered.

## Adding Tabs

Tab is a set of related groups which are combined into single item. For creating Tab, id and text properties should be specified.

{% highlight html %}

    <div id="ribbon-default"></div>
    <script src="app/ribbon/default.js"></script>
    <ul id="ribbonmenu1">
    <li><a>FILE</a>
       <ul>
         <li><a>New</a></li>
         <li><a>Open</a></li>
         <li><a>Save</a></li>
         <li><a>Save As</a></li>
         <li><a>Print</a></li>
	   </ul>
    </li>
    </ul>

{% endhighlight %}

Configure the React.createElement bind value tabs in Reactjs view-model as shown in the following code.

{% highlight html %}

	ReactDOM.render(
    React.createElement(EJ.Ribbon, { width: "50%", "applicationTab-type": "menu", "applicationTab-menuItemID": "ribbonmenu1" },
      React.createElement ("tabs", null,
        React.createElement ("tab", { id: "home", text: "HOME" },
           React.createElement ("groups", null,
		      React.createElement (
			  )
				)
        )
      )
    ),
     document.getElementById('ribbon-default')
    );

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img2.png)

## Configuring Groups

List of controls are combined as logical groups into Tab. Group alignment type as row/column, Default is row.

Create group item with text specified and add content group to Groups collection with ejButton control settings.

Configure the React.createElement bind value tabs with group and button named as New.

{% highlight html %}

	  ReactDOM.render(
    React.createElement(EJ.Ribbon, { width: "50%", "applicationTab-type": "menu", "applicationTab-menuItemID": "ribbonmenu1" },
      React.createElement("tabs", null,
        React.createElement("tab", { id: "home", text: "HOME" },
           React.createElement("groups", null,
		      React.createElement("group", { text: "New", alignType: "rows" },
			    React.createElement("content", null,
				   React.createElement("content", { "defaults-type": "button" },
				      React.createElement("groups", null,
					     React.createElement("group", { id: "new", text: "New", "buttonSettings-contentType": "imageonly", "buttonSettings-prefixIcon": "e-icon e-ribbon e-new" }
						 )
					   )
					)
				)
			  )
				)
        )
      )
    ),
    document.getElementById('ribbon-default')
    );

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img3.png)

## Adding Controls to Group

Syncfusion JavaScript Controls can be added to group’s content with corresponding type specified like button, split button, toggle button, dropdown list, gallery, custom, etc. Default type is button.

Configure the React.createElement bind value tabs with groups, button , split button and dropdown controls.Also the datasource to dropdown control is configured with bind name fontfamily.Please refer to the following code snippets.

{% highlight html %}

    var fontfamily = ["Segoe UI", "Arial", "Times New Roman", "Tahoma", "Helvetica"];
    ReactDOM.render(
    React.createElement(EJ.Ribbon, { width: "50%", "applicationTab-type": "menu", "applicationTab-menuItemID": "ribbonmenu1" },
        React.createElement("tabs", null,
        React.createElement("tab", { id: "home", text: "HOME" },
           React.createElement("groups", null,
			  React.createElement("group", { text: "SplitButton & Dropdown", alignType: "columns" },
                React.createElement("content", null,
                    React.createElement("content", { "defaults-type": "splitbutton", "defaults-width": 50, "defaults-height": 70 },
                       React.createElement("groups", null,
                           React.createElement("group", { id: "paste", text: "Paste", "customTooltip-prefixIcon": "e-pastetip", "splitButtonSettings-contentType": "imageonly", "splitButtonSettings-prefixIcon": "e-icon e-ribbon e-ribbonpaste", "splitButtonSettings-targetID": "pasteSplit1", "splitButtonSettings-buttonMode": "dropdown", "splitButtonSettings-arrowPosition": "bottom", "splitButtonSettings-click": "executeAction" }
                           )
                        )
                      ),
                      React.createElement("content", { "defaults-type": "dropdownlist", "defaults-height": 28 },
                              React.createElement("groups", null,
                                 React.createElement("group", { id: "fontfamily", "dropdownSettings-dataSource": fontfamily, "dropdownSettings-text": "Segoe UI", "dropdownSettings-select": "executeAction", "dropdownSettings-width": 150 }
                                )

                              )
                            )
                        )
                     )

				)
        )

      )
    ),
    document.getElementById('ribbon-default')
    );
  
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img4.png)