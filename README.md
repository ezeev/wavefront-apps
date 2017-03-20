# Wavefront Applications Mock

## Dummy Metrics

The apps in this repo use "dummy metrics" in order to test application definitions. Dummy metrics in this case
are Telegraf's CPU input plugin configured to emit metrics with different hostname's and prefixes.

### Example Telegraf Config:

```
[[inputs.cpu]]
  name_prefix = "wavefront.tour."
  percpu = true
  totalcpu = true
  collect_cpu_time = false
  [inputs.cpu.tags]
   hostname = "sample.app"

[[inputs.cpu]]
  name_prefix = "nginx."
  percpu = true
  totalcpu = true
  collect_cpu_time = false
  [inputs.cpu.tags]
    hostname = "nginx.hostname"

[[inputs.cpu]]
  name_prefix = "aws."
  percpu = true
  totalcpu = true
  collect_cpu_time = false
  [inputs.cpu.tags]
    hostname = "aws.ec2.hostname"
```
