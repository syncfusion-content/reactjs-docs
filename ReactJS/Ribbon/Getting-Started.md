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

Ribbon have the following list of external script dependencies and these should be referred before `ej` Script files

* [`jQuery`](http://jquery.com) 1.7.1 and later versions
* [`jQuery.easing`](http://gsgd.co.uk/sandbox/jquery/easing) - to support the animation effects in the components.

Also Ribbon have internal dependencies which includes `ej.core` libraries and [`child controls`](http://help.syncfusion.com/js/api/ejribbon#requires). For getting started, you can refer `ej.web.all.min.js` which includes `ej.core` and all Syncfusion JavaScript controls.

Add the specific theme reference to your HTML file by referring the appropriate `ej.web.all.min.css` which contains `ej.widgets.core.min.css` (layout related CSS) and `ej.theme.min.css` (theme related CSS) for all the Syncfusion controls.

Create a basic HTML file as shown below to create your Ribbon. 

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

N> 1. In case if you don’t want to use `ej.web.all.min.js` file, you can use our [`custom script generator`](http://help.syncfusion.com/js/api/ejribbon#requires) to create custom script file with required controls and its dependencies only
N> 2. Ribbon’s sample level icons can be loaded using `ej.icons.CSS` from the location **(installed location)**\ Syncfusion\Essential Studio\13.2.0.29\JavaScript\assets\css\web\ribbon-css”

## Control Initialization

The Ribbon can be configured to the HTML`<div>` element. Add a `<div>` element with Id of `Ribbon`. 

Ribbon can be initialized with `Application Tab` and UL list is needed for binding menu to application menu which can be specified through [`menuItemID`](http://help.syncfusion.com/js/api/ejribbon#members:applicationtab-menuitemid) which denotes `id` of UL.

Define the Application Tab with [`type`](http://help.syncfusion.com/js/api/ejribbon#members:applicationtab-type) as `menu` to render simple Ribbon control.


{% highlight html %}

    <div id="ribbon-resize"></div>
    <script src="app/ribbon/resize.js"></script>
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

{% highlight html %}

    ReactDOM.render(
    React.createElement(EJ.Ribbon, { width: "50%", "applicationTab-type": "menu", "applicationTab-menuItemID": "ribbonmenu1" }
    ),
    document.getElementById('ribbon-default')
    );

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img1.png)

N> Set the required [`width`](http://help.syncfusion.com/js/api/ejribbon#members:width) to Ribbon, else default parent container or window width will be considered

## Adding Tabs

Tab is a set of related groups which are combined into single item. For creating Tab, [`id`](http://help.syncfusion.com/js/api/ejribbon#members:tabs-id) and [`text`](http://help.syncfusion.com/js/api/ejribbon#members:tabs-text) properties should be specified. 

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

List of controls are combined as logical [`groups`](http://help.syncfusion.com/js/api/ejribbon#members:tabs-groups) into Tab. Group alignment type as `row/column`, Default is `row`. 

Create group item with [`text`](http://help.syncfusion.com/js/api/ejribbon#members:tabs-groups-content-groups-text) specified and add content group to Groups collection with ejButton control settings.

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

Syncfusion JavaScript Controls can be added to group’s content with corresponding [`type`](http://help.syncfusion.com/js/api/ejribbon#members:tabs-groups-type) specified like button, split button, toggle button, dropdown list, gallery, custom, etc. Default type is `button`.

{% highlight html %}

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