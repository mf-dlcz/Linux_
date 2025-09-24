# CloudWatch
The following a CloudWatch concepts.

## Metrics
- Time-ordered set of data
- Used to monitor and publish app or business activity data.
- Data point includes a time stamp and unit of measure.

## Namespaces
- is a container for CloudWatch metrics that isolates metrics from those
belonging to different apps or services.
- Each namespace must have a valid ASCII name containing 255 chars or less.
- Namespace must be specified when publishing data points to CloudWatch.
- Naming convention using '/' and service name. [AWS/EC2]

## Dimensions
- is a name-value pair that is part of the identity of a metric.
- Can assign up to 30 dimensions to a metric and use them to filter the results
that CloudWatch returns.

## Resolution
- The resolution of a metric refers to its granularity, or the time interval
between measurements.
- A metric's resolution can be **standard** or **high-resolution**.
    - **Standard** resolution metrics have a granularity of 1 min.
- When you publish a high-resolution metric, it is stored with a resolution of 1 sec.
- You can read and retrieve it with a resolution of 1, 5, 10, 30 or any multiple of 60 sec.
- **High-resolution** metrics provide more immediate insight into your apps activity, but
every **PutMetricData** call for a custom metric is charged.

## Statistic
- Are the result of data aggregation over a fixed time frame using specific dimensions and units.
- Can be produced using custom data or by other AWS services

## Percentiles
- Can be used to gain better insight into how metric data is distributed.

## Alarms
- Are automated procedures that start based on changes to a specific metric over a predetermined
period.
- Set the alarms to a period longer than or equal to the metric's resolution.
- There is a higher cost for **high-resolution** alarms.

<br>

> [!NOTE]  
> When using CloudWatch, consider resolution, frequency, alarms, and cost.