---
layout: "google"
page_title: "Google: google_compute_https_health_check"
sidebar_current: "docs-google-compute-https-health-check"
description: |-
  Manages an HTTPS Health Check within GCE.
---

# google\_compute\_https\_health\_check

Manages an HTTPS health check within GCE.  This is used to monitor instances
behind load balancers.  Timeouts or HTTPS errors cause the instance to be
removed from the pool.  For more information, see [the official
documentation](https://cloud.google.com/compute/docs/load-balancing/health-checks)
and
[API](https://cloud.google.com/compute/docs/reference/latest/httpsHealthChecks).

## Example Usage

```
resource "google_compute_https_health_check" "default" {
	name = "test"
    request_path = "/health_check"
    check_interval_sec = 1
    timeout_sec = 1
}
```

## Argument Reference

The following arguments are supported:

* `check_interval_sec` - (Optional) How often to poll each instance (default 5).

* `description` - (Optional) Textual description field.

* `healthy_threshold` - (Optional) Consecutive successes required (default 2).

* `host` - (Optional) HTTPS host header field (default instance's public ip).

* `name` - (Required) A unique name for the resource, required by GCE.
    Changing this forces a new resource to be created.

* `port` - (Optional) TCP port to connect to (default 443).

* `request_path` - (Optional) URL path to query (default /).

* `timeout_sec` - (Optional) How long before declaring failure (default 5).

* `unhealthy_threshold` - (Optional) Consecutive failures required (default 2).


## Attributes Reference

The following attributes are exported:

* `self_link` - The URL of the created resource.
