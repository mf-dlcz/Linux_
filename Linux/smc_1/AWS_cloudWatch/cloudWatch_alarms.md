# Alarm Actions
You can specify what actions an alarm takes when it changes state between the OK, 
ALARM, and INSUFFICIENT_DATA states.

## Types of Alarms
There are two types of alarms that you can create

### Metric
- Watch a single CloudWatch metric the result of a math expression based on CloudWatch metrics.
- The alarm performs one or more actions based on the result, such as sending a notification to an 
Amazon SNS topic, performing an Amazon EC2 action or an Amazon EC2 Auto Scaling action, or creating 
an OpsItem or incident in Systems Manager.

A metric alarm has the following possible states:

    - **OK**: The metric or expression is within the defined threshold.

    - **ALARM**: The metric or expression is outside the defined threshold.

    - **INSUFFICIENT_DATA**: The alarm has just started, the metric is not available, or not enough 
    data is available for the metric to determine the alarm state.

### Composite
- You can combine multiple alarms into alarm hierarchies. 
- This reduces alarm noise by initiating once when multiple alarms are initiated at the same time.

<br>

- With composite alarms, you can add logic and group alarms into a single high-level alarm, 
initiated when the underlying conditions are met.
- This means you can introduce intelligent decisions and minimize false positives.
- Composite alarms are created using one or more alarm states combined with Boolean operators AND, 
OR, and NOT and constants TRUE and FALSE. 
- A composite alarm is initiated when its expression evaluates to be TRUE.

