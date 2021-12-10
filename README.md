# regulate homework

## Scenario 1

### To launch the script what you need to do is:
1. checkout this repo:

```git clone https://github.com/lfj-s-kalikin/regulate.git```

2. navigate inside the repo directory:

```cd regulate```

3. run the script:

```./test.sh```

##### Or you if are as lazy as me you can just try it out here:
[Test Workflow](https://github.com/somedrunkbum/testofthetest/actions/workflows/test.yml)

![test workflow](https://github.com/somedrunkbum/testofthetest/actions/workflows/test.yml/badge.svg)

## Scenario 2

Taking into consideration the scenario, here is what seems interesting to monitor from my perspective. After connecting the whole system to a standard set of monitoring metrics I would highlight the following:
- System load average. Should be on every dashboard. After checking the number of cores for our CPU’s, LA for our setup should not get higher than 112. I suppose that Hyper-Threading is enabled, which makes sense for this use of the server.
- CPU load. Since the use of our server is highly CPU oriented.
- CPU io. One of the most important metrics as well, to spot bottlenecks.
- Memory usage. Operations of those kinds should be highly ‘in-memory’ processing oriented.
- SWAP use. Since our hard drive is not solid state it can dramatically impact performance.
- HDD io. Again, since it is not an SSD, it should be highly taken in consideration.
- Network throughput. Since it is crucial for the purpose of our server.

Apart from standard system monitoring, here I think what else is critical to monitor:
- Certificates expiry. If we delay it, the main purpose of the server will stop working.
- System and packages security updates. This server is decoding and proxying requests. In case of attack or control is taken over a lot of damage can be done.

Regarding applications that are used to perform described operations, I would monitor, except from the obvious:
- Request processing times. 
- Open file descriptors.
- Cache hit rate.
- Error rate. Taken from logs, or from application itself, if possible.

All that is described above can be done by using one of many modern monitoring tools of your taste. They usually support most common metrics out of the box. Then some additional things can be added by the use of plugins and extensions. If that is not enough you can: write your own scripts that gather needed information and send it to the monitoring tool; or custom metrics following description on documentation of the chosen monitoring tool.
