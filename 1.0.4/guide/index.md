# Progressbar

## 综述
* Progressbar是一个SVG动态进度条显示组件。抱着不重复造轮子的思想，它是由[progressbar](https://github.com/kimmobrunfeldt/progressbar.js)插件进行kissy的封装而来的。
* 版本：1.0.3
* 教程：[http://gallery.kissyui.com/progressbar/1.0.3/guide/index.html](http://gallery.kissyui.com/progressbar/1.0.3/guide/index.html)
* demo：[http://gallery.kissyui.com/progressbar/1.0.3/demo/index.html](http://gallery.kissyui.com/progressbar/1.0.3/demo/index.html)

## 浏览器支持
* 支持主流浏览器含 **IE9**.

## 初始化组件
		
    S.use('kg/progressbar/1.0.3/index', function (S, Progressbar) {
         var circle = new Progressbar.Circle('#landing-progress', {
             color: "#FCB03C",
             strokeWidth: 1.5,
             trailColor: null,
             fill: "#FFF9F0"
         });
         circle.animate(1, {
             duration: 1200,
             easing: 'easeInOut'
         });
    })


## API
[**ProgressBar**](#api)
* [Line(container, [*options*])](#linecontainer-options)
    * [animate(progress, [*options*], [*cb*])](#lineanimateprogress-options-cb)
    * [stop()](#linestop)
    * [set(progress)](#linesetprogress)

* [Circle(container, [*options*])](#circlecontainer-options)
    * [animate(progress, [*options*], [*cb*])](#circleanimateprogress-options-cb)
    * [stop()](#circlestop)
    * [set(progress)](#circlesetprogress)

* [Square(container, [*options*])](#squarecontainer-options)
    * [animate(progress, [*options*], [*cb*])](#squareanimateprogress-options-cb)
    * [stop()](#squarestop)
    * [set(progress)](#squaresetprogress)


## Line(container, [*options*])

Line shaped progress bar. Appends SVG to container.

**Example**

```javascript
var progressBar = new Progressbar.Line('#container', {
    strokeWidth: 2
});
```

To make line resize with its container, set for example the following CSS:

```css
.container > svg {
    display: block;
    width: 100%;
}
```

**Parameters**

* `container` Element where SVG is added. Query string or element.

    For example `"#container"` or `document.getElementById("#container")`

* `options` Options for path drawing.

    ```javascript
    {
        // Stroke color.
        // Default: "#555"
        color: "#3a3a3a",

        // Width of the stroke.
        // Unit is percentage of SVG canvas' size.
        // Default: 1.0
        strokeWidth: 0.1,

        // Color for lighter trail stroke
        // underneath the actual progress path.
        // If null, trail path is not drawn
        // Default: null
        trailColor: "#f4f4f4",

        // Duration for animation in milliseconds
        // Default: 800
        duration: 1200,

        // Easing for animation. See #easing section.
        // Default: "linear"
        easing: "easeIn"
    }
    ```
### Line.animate(progress, [*options*], [*cb*])

Animates drawing of line.

**Example**

```javascript
progressBar.animate(0.3, {
    duration: 800
}, function() {
    console.log('Animation has finished');
});
```

**Parameters**

* `progress` progress from 0 to 1.
* `options` Animation options. These options override the defaults given in initialization.

    ```javascript
    {
        // Duration for animation in milliseconds
        // Default: 800
        duration: 1200,

        // Easing for animation. See #easing section.
        // Default: "linear"
        easing: "easeOut"
    }
    ```

* `cb` Callback function which is called after transition ends.

### Line.stop()

Stops animation to its current position.

### Line.set(progress)

Sets progress instantly without animation. Clears all transitions
for path.
<br>
<br>

## Circle(container, [*options*])

Circle shaped progress bar. Appends SVG to container.

**Example**

```javascript
var progressBar = new ProgressBar.Circle('#container', {
    strokeWidth: 2
});
```

To make circle resize with its container, set for example the following CSS:

```css
.container > svg {
    display: block;
    width: 100%;
}
```

**Parameters**

* `container` Element where SVG is added. Query string or element.

    For example `"#container"` or `document.getElementById("#container")`

* `options` Options for path drawing.

    ```javascript
    {
        // Stroke color.
        // Default: "#555"
        color: "#3a3a3a",

        // Width of the stroke.
        // Unit is percentage of SVG canvas' size.
        // Default: 1.0
        strokeWidth: 0.1,

        // Color for lighter trail stroke
        // underneath the actual progress path.
        // If null, trail path is not drawn
        // Default: null
        trailColor: "#f4f4f4",

        // Fill color for the shape. If null, no fill.
        // Default: null
        fill: "rgba(0, 0, 0, 0.5)",

        // Duration for animation in milliseconds
        // Default: 800
        duration: 1200,

        // Easing for animation. See #easing section.
        // Default: "linear"
        easing: "easeIn"
    }
    ```

### Circle.animate(progress, [*options*], [*cb*])

Animates drawing of circle.

**Example**

```javascript
progressBar.animate(0.3, {
    duration: 800
}, function() {
    console.log('Animation has finished');
});
```

**Parameters**

* `progress` progress from 0 to 1.
* `options` Animation options. These options override the defaults given in initialization.

    ```javascript
    {
        // Duration for animation in milliseconds
        // Default: 800
        duration: 1200,

        // Easing for animation. See #easing section.
        // Default: "linear"
        easing: "easeOut"
    }
    ```

* `cb` Callback function which is called after transition ends.

### Circle.stop()

Stops animation to its current position.

### Circle.set(progress)

Sets progress instantly without animation. Clears all transitions
for path.
<br>
<br>

## Square(container, [*options*])

Square shaped progress bar. Appends SVG to container.

**Example**

```javascript
var progressBar = new ProgressBar.Square('#container', {
    strokeWidth: 2
});
```

To make square resize with its container, set for example the following CSS:

```css
.container > svg {
    display: block;
    width: 100%;
}
```

**Parameters**

* `container` Element where SVG is added. Query string or element.

    For example `"#container"` or `document.getElementById("#container")`

* `options` Options for path drawing.

    ```javascript
    {
        // Stroke color.
        // Default: "#555"
        color: "#3a3a3a",

        // Width of the stroke.
        // Unit is percentage of SVG canvas' size.
        // Default: 1.0
        strokeWidth: 0.1,

        // Color for lighter trail stroke
        // underneath the actual progress path.
        // If null, trail path is not drawn
        // Default: null
        trailColor: "#f4f4f4",

        // Fill color for the shape. If null, no fill.
        // Default: null
        fill: "rgba(0, 0, 0, 0.5)",

        // Duration for animation in milliseconds
        // Default: 800
        duration: 1200,

        // Easing for animation. See #easing section.
        // Default: "linear"
        easing: "easeOut"
    }
    ```

### Square.animate(progress, [*options*], [*cb*])

Animates drawing of square.

**Example**

```javascript
progressBar.animate(0.3, {
    duration: 800
}, function() {
    console.log('Animation has finished');
});
```

**Parameters**

* `progress` progress from 0 to 1.
* `options` Animation options. These options override the defaults given in initialization.

    ```javascript
    {
        // Duration for animation in milliseconds
        // Default: 800
        duration: 1200,

        // Easing for animation. See #easing section.
        // Default: "linear"
        easing: "easeInOut"
    }
    ```

* `cb` Callback function which is called after transition ends.

### Square.stop()

Stops animation to its current position.

### Square.set(progress)

Sets progress instantly without animation. Clears all transitions
for path.

## changelog

### V1.0.3

    [!]



