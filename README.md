# Why Linkerd?

The one page answer to why I think Linkerd is the best service mesh.

## Linkerd is...

### ... easy!

Linkerd is optimized for ease of use and quickly finding value and is built from the ground up with this in mind. Simplicity is an amazing feature as the tradeoff is usually expensive support contracts or large platform teams.

[Design Principles](https://linkerd.io/design-principles/)

### ... fast!

All service meshes introduce some latency, but ideally this is kept as tight as possible. Linkerd is the fastest mesh available.

[Benchmarking Linkerd and Istio: 2021 Redux](https://linkerd.io/2021/11/29/linkerd-vs-istio-benchmarks-2021/)

### ... efficient!

The resource consumption of your service meshes data plane (and to an extent the control plane) can be a signifant factor on cost and design philosophy. Does it make sense to optimize your workloads memory use when the mesh requires 150mb minimum? Linkerd will make efficient use of your compute resources with a minimal memory footprint and highly efficient CPU usage.

[Benchmarking Linkerd and Istio: 2021 Redux](https://linkerd.io/2021/11/29/linkerd-vs-istio-benchmarks-2021/)

### ... featureful!

This isn't 2019 anymore, Linkerd has come a long way and supports the most important and impactful features that a service mesh can deliver. 

* mTLS
* Retries, timeouts, circuit breakers
* Traffic splitting (Argo rollouts integration)
* Monitoring (Prometheus, Grafana, OpenTelemetry)
* Distributed tracing
* Traffic policy
* Dynamic request routing
* Zero config load balancing
* Built-in dashboard
* Tap

[Linkerd Features](https://linkerd.io/2.13/features/)

## But Linkerd doesn't...

### ... support ambient mesh / host deployed agents.

Host sidecars are shit, period. Sidecars provide an isolated resource and security context that scale proportionally with your application. Host sidecars introduce indeterministic behavior and  noisey neighbor problems. This is not desirable. Ambient mesh is a design choice meant to compensate for a _HEAVY_ data plane. This is not necessary for Linkerd because of the purpose built proxy treats your compute resources with respect.

[Per-host proxies are significantly worse than sidecars](https://buoyant.io/blog/ebpf-sidecars-and-the-future-of-the-service-mesh)

### ... have broad adoption.

The fuck you talking about? [adpters](https://github.com/linkerd/linkerd2/blob/main/ADOPTERS.md). There is also good evidence that [Linkerd is _more_ popular than Istio](https://thenewstack.io/is-linkerd-winning-the-service-mesh-race/).

### ... have proof in large production environments.

Seriously, the fuck you on about? [X-Box Cloud Gaming](https://www.cncf.io/blog/2022/05/10/service-mesh-at-scale-how-xbox-cloud-gaming-secures-22k-pods-with-linkerd%EF%BF%BC/)

### ... have the Service Mesh thought leadership.

Linkerd is created by [the people who _invented_ service mesh](https://buoyant.io/about-us). Linkerd 1 was the evolution of technology their founders worked on at Twitter ([Finnagle](https://twitter.github.io/finagle/)) which gave them early insight into the problem space at scale. They took this experience and married it with Kubernetes when creating Linkerd 2.

### ... have an API gateway.

Linkerd works and plays nicely with the rest of the CNCF ecosystem. It doesn't try to boil the ocean and solve every problem inside of a monolithic solution. Instead it opts to integrate with other leading technologies allowing operators to mix and match the tools and technologies that meet their requirements. Linkerd works very well with off the shelf ingresses such as ingress-nginx and with other commercial solutions such as [Ambassador](https://www.getambassador.io/docs/emissary/latest/howtos/linkerd2), [Kong](https://linkerd.io/2.13/tasks/using-ingress/#kong), [Nginx](https://docs.nginx.com/nginx-ingress-controller/tutorials/nginx-ingress-linkerd/), [Traefik](https://linkerd.io/2.13/tasks/using-ingress/#traefik-2x), and more.