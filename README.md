# react-live-charts ([demo](https://dsternlicht.github.io/react-live-charts/))

> Super awesome library for adding live charts visualizations to React.

[![NPM](https://img.shields.io/npm/v/react-live-charts.svg)](https://www.npmjs.com/package/react-live-charts) [![Build Status](https://travis-ci.com/dsternlicht/react-live-charts.svg?branch=master)](https://travis-ci.com/dsternlicht/react-live-charts) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

[![Demo](https://raw.githubusercontent.com/dsternlicht/react-live-charts/master/example/demo.gif)](https://dsternlicht.github.io/react-live-charts/)

## Install

```bash
npm install --save react-live-charts
```

## Usage

Check out the [Demo](https://dsternlicht.github.io/react-live-charts/) to see it in action.

```jsx
import React, { Component } from 'react'

import { LiveBarChart } from 'react-live-charts'

class App extends Component {
  state = {
    data: [
      // ...
    ]
  };

  render () {
    return (
      <LiveBarChart
        data={this.state.data}
      />
    )
  }
}
```

## Props

| Property      | Type               | Default                               | Description                                                                                                                                  |
|:--------------|:-------------------|:--------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------|
| `data`  | array           | []                                  | An array of objects that contain the data of the chart. |
| `baseline`  | number           | null                                  | If you want the chart to have a baseline, add its number here. Could be useful for charts that include negative values |
| `iterationTimeout`  | number           | 200                         | Number of milliseconds you want between iterations. |
| `startAutomatically`  | boolean           | true                                  | Whether the visualization should start running automatically. Default is `true` |
| `startRunningTimeout`  | number           | 0                         | Number of milliseconds you want before running the visualization. |
| `onRunStart`  | function           | null                                  | A callback function that being called once the visualization **starts** |
| `onRunEnd`  | function           | null                                  | A callback function that being called once the visualization **ends** |
| `showTitle`  | boolean           | true                                  | Whether you want to show each iteration's title |
| `barHeight`  | number           | 50                                  | The height (in pixels) of each bar item |
| `mainWrapperStyles`  | object           | {}                                  | Styles object for the component's main wrapper |
| `chartWrapperStyles`  | object           | {}                                  | Styles object for the chart wrapper |
| `baselineStyles`  | object           | {}                                  | Styles object for the baseline element |
| `iterationTitleStyles`  | object           | {}                                  | Styles object for the title element |
| `labelStyles`  | object           | {}                                  | Styles object for the chart's labels |

## Data

The `data` property in expected to be an array of objects. Each object will present an interation and will include the following fields:

| Property      | Type          | Description                                                                                                                                  |
|:--------------|:-------------------|:---------------------------------------------------------------------------------------------------------------------------------------------|
| `name` | string | The name of the iteration. 
| `values` | array | An array of data objects (see below).

Each value in the `values` array will contain the following properties:

| Property      | Type          | Description                                                                                                                                  |
|:--------------|:-------------------|:---------------------------------------------------------------------------------------------------------------------------------------------|
| `id` | string / number | A unique idetifier for the item. Note that it should be consistent across all interations. |
| `label` | string / React Node | The label of the item. |
| `value` | number | A numeric value of the item |

## License

MIT © [Daniel Sternlicht](https://github.com/dsternlicht)