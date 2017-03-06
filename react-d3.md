
Saved 2 minutes ago
MARKDOWN TIPS
PREVIEW
PUBLISH



Using D3.JS with React

Click to set cover photo







​
##Creating or using a graph library.
​
There are many great graphing libraries our there, ChartJS, HighCharts and D3.js (more specifically react-d3 and rd3) that will get your started creating graphs for your apps. However sometimes your dataset can be too unique to display via simple charts that came with the standard library. Utilizing one of these librarys would require a re-write of some of the components or create new ones by piecemealing different graphs components together. 
​
You can use D3.js when a charting library simply won’t cut it. The main principle of D3 is to enable developers to programmatically construct SVG objects and render them as they see fit. Below is an example of creating a unique BarLine Graph with resuable react components.
​
##Creating the Graphs into Reusable React Components
Because of the complexity of the data and wanting to focus on showing you how we created reusable react.js components. I want to show how we went from raw D3.js javascript to mapping it to a react.js component with a simple bar graph. The end result looked like this graph below. We were able to reuse the line and bar components in our other charts as well.
​
###Creating the Bars
In D3 creating a bar for a bar graph is pretty easy it is just a group of SVG rectangles drawn to the screen. We created a simple component to allow us to configure the individual bars we want to write to the screen.
​
```
import React from 'react';
​
const Bar = (props) => {
  return (
    <rect
      className={props.className}
      {...props}
    />
  );
}
​
Bar.propTypes = {
  fill: React.PropTypes.string,
  width: React.PropTypes.number,
  height: React.PropTypes.number,
  x: React.PropTypes.number,
  y: React.PropTypes.number,
  className: React.PropTypes.string
}
​
Bar.defaultProps = { className: 'barchart-bar' };
​
export default bar;
```
​
###Creating the Line
In D3 you create a path to plot data points on the screen, and then draw a line between the points.
```
import React from 'react';
​
const Path = (props) => {
  return (
    <path
      className={props.class}
      d={props.path}
      {...props} />
  );
}
​
Path.propTypes = {
  fill: React.PropTypes.string,
  path: React.PropTypes.string,
  stroke: React.PropTypes.string,
  strokeWidth: React.PropTypes.number,
  className: React.PropTypes.string
}
​
Path.defaultProps = { className: 'linechart-path' };
​
export default Path;
```
​
###Creating the Axis
​
###Creating the BarLine Graph
​
###Putting it together
Now the hard part, putting it together and scaling it.
​
![Screenshot 2016-10-04 11.30.40.png](https://cdn.filestackcontent.com/fyOpzjCfTIOgEeqCTlTr)
​
