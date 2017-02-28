---
layout: post
title:  Globalization and Localization
description: Globalization and Localization
documentation: ug
platform: React JS
keywords: globalization and localization,kanban globalization and localizationards
---

# Localization

## Localization

All text in Kanban can be localized using `ej.Kanban.Locale` object. Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
EmptyCard
</td><td>
No cards to display
</td></tr>
<tr>
<td>
SaveButton
</td><td>
Save
</td></tr>
<tr>
<td>
CancelButton
</td><td>
Cancel
</td></tr>
<tr>
<td>
EditFormTitle
</td><td>
Details of
</td></tr>
<tr>
<td>
AddFormTitle
</td><td>
Add New Card
</td></tr>
<tr>
<td>
SwimlaneCaptionFormat
</td><td>
"- {{:count}}{{if count == 1 }} item {{else}} items {{/if}}"
</td></tr>
<tr>
<td>
FilterSettings
</td><td>
Filters:
</td></tr>
<tr>
<td>
Min
</td><td>
Min
</td></tr>
<tr>
<td>
Max
</td><td>
Max
</td></tr>
<tr>
<td>
FilterOfText
</td><td>
Of
</td></tr>
<tr>
<td>
Cards
</td><td>
Cards
</td></tr>
<tr>
<td>
ItemsCount
</td><td>
Items Count :
</td></tr>
<tr>
<td>
Unassigned
</td><td>
Unassigned
</td></tr>
</table>

The following code example describes the above behavior.

{% highlight html %}

var data = ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(20));
ej.Kanban.Locale["de-DE"] = {
            EmptyCard: "Keine Karten angezeigt werden",
            SaveButton: "Speichern",
            CancelButton: "stornieren",
            EditFormTitle: "Details von ",
            AddFormTitle: "Neue Karte hinzufügen",
            SwimlaneCaptionFormat: "- 8 Artikel  Artikel ",
            FilterSettings: "Filter:",
            FilterOfText: "Von",
            Max: "Max.",
            Min: "Min.",
			Cards: "  Karten",
			ItemsCount:"Artikel Graf :",
			Unassigned: "Nicht zugewiesen",
        };
ReactDOM.render(
<EJ.Kanban dataSource={data} locale="de-DE" keyField="Status" fields-content="Summary" fields-primaryKey="Id" fields-tag="Tags" fields-swimlaneKey="Assignee" enableTotalCount={true}>
    <columns>
		<column headerText="Backlog" key="Open"></column>
		<column headerText="In Progress" key="InProgress" constraints-max="2"></column>
	    <column headerText="Done" key="Close"></column>
	</columns>
</EJ.Kanban>,
   document.getElementById('kanbanboard-default')
);

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Localization_images/localization_img1.png)


