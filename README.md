# UI5 Custom Control: Chart.js

This project includes a custom control which can be consumed as a standard Node/NPM package.json dependency. It provides a wrapper for Chart.js for a LineChart.

## Usage

Install the dependency to your UI5 project:

```sh
npm install ui5-cc-chart
```

Include the `ui5-tooling-modules` tooling extensions to your UI5 project:

```sh
npm install ui5-tooling-modules -D
```

Add the `ui5-tooling-modules` task and middleware to your `ui5.yaml`:

```yaml
specVersion: "2.0"
[...]
builder:
  customTasks:
    - name: ui5-tooling-modules-task
      afterTask: replaceVersion
[...]
server:
  customMiddleware:
    - name: ui5-tooling-modules-middleware
      afterMiddleware: compression
[...]
```

Now you can use the control either in an `XMLView`:

```xml
<mvc:View controllerName="my.Controller" 
          xmlns:mvc="sap.ui.core.mvc" 
          xmlns:chart="ui5-cc-chart">
[...]
    <chart:Chart type="line" title="Some Chart" color="green">
        <chart:ChartRecord label="Day 1" value="100" />
        <chart:ChartRecord label="Day 2" value="50" />
    </chart:Chart>
[...]
</mvc:View>
```

or in your JavaScript code:

```js
sap.ui.define([..., "ui5-cc-chart/Chart", "ui5-cc-chart/Chart"], function(..., Chart, ChartRecord) {

    [...]

    new Chart({
        type: "line",
        title: "Some Chart",
        color: "green",
        records: [
            new ChartRecord({label: "Day 1", value: 100}),
            new ChartRecord({label: "Day 2", value: 50})
        ]
    })

    [...]

});
```

## How to obtain support

Please use the GitHub bug tracking system to post questions, bug reports or to create pull requests.

## Contributing

Any type of contribution (code contributions, pull requests, issues) to this showcase will be equally appreciated.

## License

This work is [dual-licensed](../../LICENSE) under Apache 2.0 and the Derived Beer-ware License. The official license will be Apache 2.0 but finally you can choose between one of them if you use this work.

When you like this stuff, buy [@mianbsp](https://twitter.com/mianbsp) a beer or buy [@pmuessig](https://twitter.com/pmuessig) a coke when you see them.
