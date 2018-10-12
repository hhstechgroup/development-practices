# Health Checks

All digital service apps should have a /system-information endpoint which provides the following:

* HTTP Status 200 if system is healthy
* HTTP Status 465 if any health check fails (This is an unused http code because these are used by our load balancer which determines if a service should be rotated out based on a a non-200 status code.)
* The body response is defined as JSON in either case and follows this standard:
  * `application` *required*
  * `version` *required*
  * `health_status` *required* (true/false)
  * `health_checks`:
    * `healthy` *required* (true/false)

## JSON template:

```json
{
  "application": "<application name>",
  "version": "<application version>",
  "build": "<jenkins build number (optional)>",
  "git_commit": "<git commit hash (optional)>",
  "<parameter 1 (optional)>": "<some value>",
  "<parameter 2 (optional)>": "<some value>",
  "<parameter N (optional)>": "<some value>",
  "health_status": false,
  "health_checks": {
    "check_item_1": {
      "healthy": true,
      "message": "Some text message (optional)",
      "timestamp": "2018-09-20T13:12:20.784-07:00 (optional)"
    },
    "check_item_2": {
      "healthy": false,
      "message": "Some text message (optional)",
      "timestamp": "2018-09-20T13:12:20.784-07:00 (optional)"
    },
    "check_item_N": {
      "healthy": false,
      "message": "Some text message (optional)",
      "timestamp": "2018-09-20T13:12:20.784-07:00 (optional)"
    }
  }
}
```
