https://cloud.google.com/istio/docs/istio-on-gke/overview#modifying_control_plane_settings

kubectl -n istio-system edit rule stackdriver-tracing-rule

Change
    Match:  context.protocol == "http" || context.protocol == "grpc"

to
    Match:  (context.protocol == "http" || context.protocol == "grpc") && request.path != "/healthz"

Installing Prometheus

https://cloud.google.com/istio/docs/istio-on-gke/installing#adding_prometheus

https://github.com/istio/istio/issues/6593#issuecomment-434981452
