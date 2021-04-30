# d3.tip: Tooltips for d3.js visualizations

[![](https://github-images.s3.amazonaws.com/skitch/Screen_Shot_2013-04-08_at_11.40.10_AM-20130408-114054.png)](http://bl.ocks.org/Caged/6476579)

This fork fixes 2 long standing issues with the original (now archived) d3-tip:
* The rootElement configuration had a bug which meant it couldn't be used.
* Using the rootElement config would cause the tooltips to display in the wrong place (even completely off the screen) when it was inside a scrollable ancestor or any ancestor with `position: relative`.

* [See a live demo (of the original fork)](http://bl.ocks.org/Caged/6476579)
* [Example code](/examples)

### API Docs
See the [API Documentation](docs/index.md)

### Download Latest Version
* [Development Version](https://raw.github.com/TheAfterman/d3-tip/master/index.js) : **6kb** / **~2kb gzipped**

### Install with NPM
```
npm install d3-tip-2021
```

### Quick Usage
```javascript
/* Initialize tooltip */
tip = d3.tip().attr('class', 'd3-tip').html(function(d) { return d; });

/* Invoke the tip in the context of your visualization */
vis.call(tip)

vis.selectAll('rect')
  .data(data)
  .enter()
  .append('rect')
  .attr('width', function() { return x.rangeBand() })
  .attr('height', function(d) { return h - y(d) })
  .attr('y', function(d) { return y(d) })
  .attr('x', function(d, i) { return x(i) })
  .on('mouseover', tip.show)
  .on('mouseout', tip.hide)
```

If you want basic styling, you can include `example-styles.css` using a service like
rawgithub.com.

```html
<link rel="stylesheet" href="//rawgithub.com/Caged/d3-tip/master/examples/example-styles.css">
```
