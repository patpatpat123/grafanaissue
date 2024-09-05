# grafanaissue
We now migrate to the latest springboot.

Since 3.3, there is the prometheus change:
https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-3.3-Release-Notes#prometheus-client-1x
https://github.com/micrometer-metrics/micrometer/wiki/1.13-Migration-Guide

And as you can see in the pom, there is the new registry.
```
		<dependency>
			<groupId>io.micrometer</groupId>
			<artifactId>micrometer-registry-prometheus-simpleclient</artifactId>
		</dependency>
```

With the configuration 
```
management.prometheus.metrics.export.pushgateway.enabled=true
management.prometheus.metrics.export.pushgateway.base-url=https://prometheus-prod-36-prod-us-west-0.grafana.net/api/prom/push
```

However, there is nothing sent to grafana cloud anymore. (please see screenshot in resource)

What is the issue?
