---
title: Essential JavaScript ReportDesigner dependencies
description: Listed ReportDesigner internal and external dependencies
platform: ReactJS
control: ReportDesigner
documentation: ug
---
# Dependencies

## React JS

The following list of external dependencies are mandatory in order to render any of the Syncfusion controls - 

* [`jQuery`](http://jquery.com "jQuery") 1.7.1 and later versions.

* [`jsRender`](https://github.com/borismoore/jsrender "jsRender") - to render the templates.

The required **ReactJS** script dependencies are as follows.

* `react.min.js` - [http://cdn.syncfusion.com/js/assets/external/react.min.js](http://cdn.syncfusion.com/js/assets/external/react.min.js)

* `react-dom.min.js` - [http://cdn.syncfusion.com/js/assets/external/react-dom.min.js](http://cdn.syncfusion.com/js/assets/external/react-dom.min.js)

* `browser.min.js` - [http://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js](http://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js)

The other required external dependencies of ReportDesigner are,

* [`CodeMirror`](https://github.com/codemirror/CodeMirror "CodeMirror") - to edit the SQL queries with syntax highlighter.

And the internal dependencies are tabulated below.

<table>
    <tr>
        <th>
            File
        </th>
        <th>
            Description/Usage
        </th>
    </tr>
    <tr>
        <td>
            ej.core.min.js
        </td>
        <td>
            Must be referred always before using all the JS controls
        </td>
    </tr>
    <tr>
        <td>
            ej.data.js
        </td>
        <td>
            Used to handle data operation and should be used while binding data to JS controls
        </td>
    </tr>
    <tr>
        <td>
            ej.draggable.js
        </td>
        <td>
          Used to handle drag on drop operation in all JS controls
        </td>
    </tr>
    <tr>
        <td>
            ej.scroller.js
        </td>
        <td>
           Used to handle scrolling operation in all JS controls
        </td>
    </tr>
    <tr>
        <td>
            ej.globalize.js
        </td>
        <td>
          It is referred when using localization in ReportDesigner
        </td>
    </tr>
    <tr>
        <td>
            ej.waitingpopup.js
        </td>
        <td rowspan="32">
        These files are used to handle the internal UI and actions of ReportDesigner.
        </td>
    </tr>
    <tr>
        <td>
            ej.button.js
        </td>
    </tr>
    <tr>
        <td>
            ej.checkbox.js
        </td>
    </tr>
    <tr>
        <td>
            ej.radiobutton.js
        </td>
    </tr>
    <tr>
        <td>
            ej.autocomplete.js
        </td>
    </tr>
    <tr>
        <td>
            ej.datepicker.js
        </td>
    </tr>
    <tr>
        <td>
            ej.timepicker.js
        </td>
    </tr>
    <tr>
        <td>
            ej.datetimepicker.js
        </td>
    </tr>
    <tr>
        <td>
            ej.daterangepicker.js
        </td>
    </tr>
    <tr>
        <td>
            ej.dialog.js
        </td>
    </tr>
    <tr>
        <td>
            ej.dropdownlist.js
        </td>
    </tr>
    <tr>
        <td>
            ej.tooltip.js
        </td>
    </tr>
    <tr>
        <td>
            ej.listbox.js
        </td>
    </tr>
    <tr>
        <td>
            ej.map.js
        </td>
    </tr>
    <tr>
        <td>
            ej.editor.js
        </td>
    </tr>
    <tr>
        <td>
            ej.maskedit.js
        </td>
    </tr>
    <tr>
        <td>
            ej.menu.js
        </td>
    </tr>
    <tr>
        <td>
            ej.pager.js
        </td>
    </tr>
    <tr>
        <td>
            ej.slider.js
        </td>
    </tr>
    <tr>
        <td>
            ej.splitter.js
        </td>
    </tr>        
    <tr>
        <td>
            ej.splitbutton.js
        </td>
    </tr>
    <tr>
        <td>
            ej.toolbar.js
        </td>
    </tr>
    <tr>
        <td>
            ej.tab.js
        </td>
    </tr>
    <tr>
        <td>
            ej.treeview.js
        </td>
    </tr>
    <tr>
        <td>
            ej.uploadbox.js
        </td>
    </tr>
    <tr>
        <td>
            ej.colorpicker.js
        </td>
    </tr>
    <tr>
        <td>
            ej.grid.js
        </td>
    </tr>
    <tr>
        <td>
            ej.reportViewer.js
        </td>
    </tr>
    <tr>
        <td>
            ej.chart.js
        </td>
    </tr>
    <tr>
        <td>
            ej.circulargauge.js
        </td>
    </tr>
    <tr>
        <td>
            ej.lineargauge.js
        </td>
    </tr>
    <tr>
        <td>
            ej.bulletgraph.js
        </td>
    </tr>

</table>

## API Service

External assemblies needed for ReportDesigner service are tabulated below.

<table>
    <tr>
        <th>
            Assemblies
        </th>
        <th>
            Description/Usage
        </th>
    </tr>
    <tr>
        <td>
            System.Web.Http
        </td>
        <td rowspan="6">
            Must be referred these assemblies for WebAPI.
        </td>
    </tr>
    <tr>
        <td>
            System.Web.Http.WebHost
        </td>
    </tr>
    <tr>
        <td>
            System.Net.Http.WebRequest
        </td>
    </tr>
    <tr>
        <td>
            System.Net.Http.Formatting
        </td>
    </tr>
    <tr>
        <td>
            System.Net.Http
        </td>
    </tr>    
    <tr>
        <td>
            System.Web.Routing
        </td>
    </tr>        
</table>

And the internal assemblies are tabulated below.

<table>
    <tr>
        <th>
            Assemblies
        </th>
        <th>
            Description/Usage
        </th>
    </tr>
    <tr>
        <td>
            Syncfusion.Shared.Wpf
        </td>
        <td>
            It's common dependencies for our WPF components which will be used to handle the report export related actions in ReportViewer.
        </td>
    </tr>
    <tr>
        <td>
           Syncfusion.Pdf.Base
        </td>
        <td>
          Must be referred to handle pdf export.
        </td>        
    </tr>
    <tr>
        <td>
            Syncfusion.DocIO.Base
        </td>
        <td>
          Must be referred to handle word export.        
        </td>        
    </tr>
    <tr>
        <td>
            Syncfusion.XlsIO.Base
        </td>
        <td>
          Must be referred to handle excel export.        
        </td>        
    </tr>
    <tr>
        <td>
            Syncfusion.Presentation.Base
        </td>
        <td>
          Must be referred to handle ppt export.        
        </td>        
    </tr>
    <tr>
        <td>
            Syncfusion.Chart.Wpf
        </td>
        <td>
          Must be referred to export the chart item from ReportViewer.        
        </td>        
    </tr>
    <tr>
        <td>
            Syncfusion.Gauge.Wpf
        </td>
        <td>
          Must be referred to export the Gauge item from ReportViewer.                
        </td>        
    </tr>
    <tr>
        <td>
            Syncfusion.SfMaps.Wpf
        </td>
        <td>
          Must be referred to export the Map item from ReportViewer.                
        </td>        
    </tr>
    <tr>
        <td>
            Syncfusion.EJ.ReportViewer
        </td>
        <td>
          It's used to preview the report.        
        </td>        
    </tr>
    
</table>
