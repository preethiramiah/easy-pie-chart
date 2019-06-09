
## Get started
#### Installation
#### Vanilla JS

```html
<div class="chart" data-percent="73">73%</div>

<script src="/path/to/easy-pie-chart.js"></script>
<script>
    var element = document.querySelector('.chart');
    new EasyPieChart(element, {
        // your options goes here
    });
</script>
```

## Options
You can pass these options to the initialize function to set a custom look and feel for the plugin.

<table>
    <tr>
        <th>Property (Type)</th>
        <th>Default</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><strong>barColor</strong></td>
        <td>#ef1e25</td>
        <td>The color of the curcular bar. You can either pass a valid css color string, or a function that takes the current percentage as a value and returns a valid css color string.</td>
    </tr>
    <tr>
        <td><strong>trackColor</strong></td>
        <td>#f2f2f2</td>
        <td>The color of the track, or false to disable rendering.</td>
    </tr>
    <tr>
        <td><strong>scaleColor</strong></td>
        <td>#dfe0e0</td>
        <td>The color of the scale lines, false to disable rendering.</td>
    </tr>
    <tr>
        <td><strong>scaleLength</strong></td>
        <td>5</td>
        <td>Length of the scale lines (reduces the radius of the chart).</td>
    </tr>
    <tr>
        <td><strong>lineCap</strong></td>
        <td>round</td>
        <td>Defines how the ending of the bar line looks like. Possible values are: <code>butt</code>, <code>round</code> and <code>square</code>.</td>
    </tr>
    <tr>
        <td><strong>lineWidth</strong></td>
        <td>3</td>
        <td>Width of the chart line in px.</td>
    </tr>
    <tr>
        <td><strong>size</strong></td>
        <td>110</td>
        <td>Size of the pie chart in px. It will always be a square.</td>
    </tr>
        <tr>
        <td><strong>rotate</strong></td>
        <td>0</td>
        <td>Rotation of the complete chart in degrees.</td>
    </tr>
    <tr>
        <td><strong>animate</strong></td>
        <td>object</td>
        <td>Object with time in milliseconds and boolean for an animation of the bar growing (<code>{ duration: 1000, enabled: true }</code>), or false to deactivate animations.</td>
    </tr>
    <tr>
        <td><strong>easing</strong></td>
        <td>defaultEasing</td>
        <td>Easing function or string with the name of a <a href="http://gsgd.co.uk/sandbox/jquery/easing/" target="_blank">jQuery easing function</a></td>
    </tr>
    <tr>
        <td><strong>imagePath</strong></td>
        <td>https://static-ssl.businessinsider.com/image/59f8dc483e9d25db458b5dfc-2400/gettyimages-645671866.jpg</td>
        <td>URL of the image to be displayed near the loading bar of the chart.</td>
    </tr>
</table>


## Callbacks
All callbacks will only be called if `animate` is not `false`.

<table>
    <tr>
        <th>Callback(params, ...)</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><strong>onStart(from, to)</strong></td>
        <td>Is called at the start of any animation.</td>
    </tr>
    <tr>
        <td><strong>onStep(from, to, currentValue)</strong></td>
        <td>Is called during animations providing the current value (the method is scoped to the context of th eplugin, so you can access the DOM element via <code>this.el</code>).</td>
    </tr>
    <tr>
        <td><strong>onStop(from, to)</strong></td>
        <td>Is called at the end of any animation.</td>
    </tr>
</table>



## Plugin api
#### Vanilla JS

```javascript
// instantiate the plugin
var chart = new EasyPieChart(element, options);
// update
chart.update(40);
// disable animation
chart.disableAnimation();
// enable animation
chart.enableAnimation();
```

###### Using a gradient

```javascript
new EasyPieChart(element, {
  barColor: function(percent) {
    var ctx = this.renderer.getCtx();
    var canvas = this.renderer.getCanvas();
    var gradient = ctx.createLinearGradient(0,0,canvas.width,0);
        gradient.addColorStop(0, "#ffe57e");
        gradient.addColorStop(1, "#de5900");
    return gradient;
  }
});
```
## Browser Support
Native support

* Chrome
* Safari
* FireFox
* Opera
* Internet Explorer 9+


## Credits
Thanks to [Rafal Bromirski](http://www.paranoida.com/) for designing [this dribble shot](http://drbl.in/ezuc) which inspired me building this plugin.


## Copyright
Copyright (c) 2015 Robert Fleischmann, contributors. Released under the MIT, GPL licenses
