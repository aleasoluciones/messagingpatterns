By default publish all the interesting info/event to a common exchange (events) using a routing key that identify the event and the datacenter source
Very useful for:
- state change of devices
- app events
- metrics

The events are consumed by various processes each one with it's queue.
The events can be resend to a central broker (using federation)
The central broker / the flow of (resend) events can be used for:
- Development of features that can be deployed on each datacenter or on a central location
- Features that aggregate info from various datacenters
- Detect anomalies/variations on the event flow
