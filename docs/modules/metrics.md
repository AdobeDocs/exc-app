**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / metrics

# Module: metrics

API used to log messages, errors, events, metrics and analytics that get pushed to our telemetry
system.

The main goal of this project is to provide solutions that are integrating with Unified-Shell and
running on Adobe Experience Cloud as much telemetry information as possible "for free" and a
convenient integration option to collect custom, application specific metrics.

***Import:***

```typescript
import metrics from '@adobe/exc-app/metrics';
```

***Type:***

[MetricsApi](../interfaces/metrics.metricsapi.md#interface-metricsapi)

***Usage:***

```typescript
import metrics from '@adobe/exc-app/metrics';

class MyClass {
  constructor() {
    this.metrics = metrics.create('exc.landing-page.recents');
  }

  async someOperation() {
    const timer = this.metrics.start('MyClass.someOperation');
    try {
      await performOperation();
      timer.time('done');
    } catch(err) {
      this.metrics.error(error);
      throw err;
    }
  }
}
```

## Index

### Enumerations

* [RecordType](../enums/metrics.recordtype.md)

### Interfaces

* [Analytics](../interfaces/metrics.analytics.md)
* [History](../interfaces/metrics.history.md)
* [Metric](../interfaces/metrics.metric.md)
* [Metrics](../interfaces/metrics.metrics-1.md)
* [MetricsApi](../interfaces/metrics.metricsapi.md)
* [Timer](../interfaces/metrics.timer.md)
