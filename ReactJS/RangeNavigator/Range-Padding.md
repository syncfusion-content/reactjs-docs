---
layout: post
title: Range-Padding
description: Range Padding
platform: js
control: RangeNavigator
documentation: ug
---

### Range Padding

**Range Padding** adds padding for range in **RangeNavigator**. It allows you to space the grid lines in the **RangeNavigator**.  By default, this property is set to **none**.

#### Numeric

The **rangePadding** property allows you to customize the automatic range calculation using the default auto range calculation for **RangeNavigator**.

{% highlight html %}

ReactDOM.render(
                     <EJ.RangeNavigator id="rangenavigator1"     valueType ="numeric" 
                      rangePadding = 'none ' ></EJ.RangeNavigator>,                    
                     document.getElementById('rangenavigator')
);


{% endhighlight %}

##### None

By default, the **rangePadding** for numerical range is none. The range is calculated from the minimum value to the maximum value of data in the RangeNavigator.

The following screenshot illustrates a **RangeNavigator** with **rangePadding** set to none.



![](/js/RangeNavigator/Range-Padding_images/Range-Padding_img1.png) 

##### Additional

When you set the **rangePadding** for numerical range to **Additional**, range is padded with an interval.

The following screenshot illustrates a **RangeNavigator** with **rangePadding** set to additional.



![](/js/RangeNavigator/Range-Padding_images/Range-Padding_img2.png) 

##### Normal

In normal **rangePadding**, automatic range calculation differs based on the data. 

The following screenshot illustrates **RangeNavigator** with **rangePadding** set to normal

![](/js/RangeNavigator/Range-Padding_images/Range-Padding_img3.png) 

##### Round

Round **rangePadding** for a numerical range rounds the range of the control to the nearest possible value that is divisible by the interval.

The following screenshot illustrates a **RangeNavigator** with **rangePadding** set to **Round**.

![](/js/RangeNavigator/Range-Padding_images/Range-Padding_img4.png) 

#### DateTime

Using the default range calculation for **RangeNavigator**, the **rangePadding** property allows you to customize the range.

{% highlight html %}


ReactDOM.render(
              <EJ.RangeNavigator id="rangenavigator1"     valueType ="dateTime" 
              rangePadding = 'none ' ></EJ.RangeNavigator>,
              document.getElementById('rangenavigator')
);


{% endhighlight %}

##### None

By default, the **rangePadding** for **DateTime** range is none. The range is calculated from the minimum value to the maximum value of data in the RangeNavigator

The following screenshot illustrates a **RangeNavigator** with **rangePadding** set to none.

![](/js/RangeNavigator/Range-Padding_images/Range-Padding_img5.png) 

##### Round

Round **rangePadding** for a **DateTime** range rounds the range of the control to the nearest possible value.

The following screenshot illustrates a **RangeNavigator** with **rangePadding** set to Round.

![](/js/RangeNavigator/Range-Padding_images/Range-Padding_img6.png) 

### Customize axis range of navigator

**RangeNavigator** calculates the range automatically based on the values of series data points. However you can explicitly specify the range using the **start**, **end** properties in **rangeSettings** that is not possible when data is provided.

The following code example renders a RangeNavigator with a range from 2010 January 1st to 2013 January 1st.

{% highlight html %}

var rangeSettings = {
                    start: "2010/1/1", end: "2012/13/1"
                };
ReactDOM.render(
                <EJ.RangeNavigator id="rangenavigator1" rangeSettings = {rangeSettings}   ></EJ.RangeNavigator>,
                document.getElementById('rangenavigator')
);


{% endhighlight %}


![](/js/RangeNavigator/Range-Padding_images/Range-Padding_img7.png) 
