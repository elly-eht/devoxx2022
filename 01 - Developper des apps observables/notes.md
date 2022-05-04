# Develop observable application in production

`An application generates value only when it runs, not when it's developed`

As no one really likes to debug without any clue, it's important to know what's happening with the application.

To do so, we need metrics/KPIs.

## Monitoring vs Observability

### Monitoring

It provides ways to know if a system is working. 

It's based on specific sets of metrics or logs. Teams will then collect those information and compare it with predefined thresholds.

Ex : response_time > 500 ms => App is slow

### Observability

The more complex an app is, the more challenging it is to fix it. 

Observability is a set of tools, metrics, logs etc... to allow teams to actively debug a system. It goes further than monitoring as it can help with finding why it is not working and how to fix it (if done well). 

Ex : Combining server metrics and flame graph to understand which function is making the app slow.

## Debugging

Debugging is the process which leads to the understanding of a system.

It **has** to be done in production, while the app is running. No "reboot" or random changes in production,"hoping" it'll fix it. 

### How to debug ?

1. ask questions
2. answer questions with observations
3. loop back until system is working as intended

It's even more helpful if we could write code that can answer those questions about itself.

### How to write debuggable app ? 

Make it observable.

Modify source code to add meaningful logs, metrics or traces.

Or add agent which can emit data about the system's state (ex: prometheus).

#### Logs

A meaningful log includes : 
- the context
- the error itself
- how to fix it

#### Metrics

For each app, we need to measure : 
- usage
- latency
- saturation
- errors

#### Tracing

Great way to follow a request and retrieve its logs and metrics

### Visualization

Use multiple tools to visualize data (flamegraphs, graphs, logs, tracing UI etc...)

It helps with detecting patterns, providing answers and raising new questions. 
