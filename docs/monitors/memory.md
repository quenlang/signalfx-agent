<!--- GENERATED BY gomplate from scripts/docs/monitor-page.md.tmpl --->

# memory


This monitor reports memory and memory utilization metrics.

On Linux hosts, this monitor relies on the `/proc` filesystem.
If the underlying host's `/proc` file system is mounted somewhere other than
/proc please specify the path using the top level configuration `procPath`.

```yaml
procPath: /proc
monitors:
 - type: memory
```


Monitor Type: `memory`

[Monitor Source Code](https://github.com/signalfx/signalfx-agent/tree/master/internal/monitors/memory)

**Accepts Endpoints**: No

**Multiple Instances Allowed**: **No**

## Configuration

This monitor has no configuration options.


## Metrics

The following table lists the metrics available for this monitor. Metrics that are not marked as Custom are standard metrics and are monitored by default.

| Name | Type | Custom | Description |
| ---  | ---  | ---    | ---         |
| `memory.available` | gauge | X | (Windows Only) Bytes of memory available for use. |
| `memory.buffered` | gauge |  | (Linux Only) Bytes of memory used for buffering I/O. |
| `memory.cached` | gauge |  | (Linux Only) Bytes of memory used for disk caching. |
| `memory.free` | gauge |  | (Linux Only) Bytes of memory available for use. |
| `memory.slab_recl` | gauge |  | (Linux Only) Bytes of memory, used for SLAB-allocation of kernel objects, that can be reclaimed. |
| `memory.slab_unrecl` | gauge |  | (Linux Only) Bytes of memory, used for SLAB-allocation of kernel objects, that can't be reclaimed. |
| `memory.used` | gauge |  | Bytes of memory in use by the system. |
| `memory.utilization` | gauge |  | Percent of memory in use on this host. This metric reports with plugin dimension set to "signalfx-metadata". |


To specify custom metrics you want to monitor, add a `metricsToInclude` filter
to the agent configuration, as shown in the code snippet below. The snippet
lists all available custom metrics. You can copy and paste the snippet into
your configuration file, then delete any custom metrics that you do not want
sent.

Note that some of the custom metrics require you to set a flag as well as add
them to the list. Check the monitor configuration file to see if a flag is
required for gathering additional metrics.

```yaml

metricsToInclude:
  - metricNames:
    - memory.available
    monitorType: memory
```



