# Changelog

## [0.18.0] November 20, 2017
[0.18.0]: https://github.com/datawire/ambassador/compare/v0.17.0...v0.18.0

### Changed

- The Host header is no longer overwritten when Ambassador talks to an external auth service. It will now retain whatever value the client passes there.

### Fixed

- Checks for updates weren’t working, and they have been restored. At present you’ll only see them in the Kubernetes logs if you’re using annotations to configure Ambassador — they’ll start showing up in the diagnostics service in the next release or so.

## [0.17.0] November 14, 2017
[0.17.0]: https://github.com/datawire/ambassador/compare/v0.16.0...v0.17.0

### Changed

- Allow Mappings to require matches on HTTP headers and `Host`
- Update tests, docs, and diagnostic service for header matching

### Fixed

- Published YAML resource files will no longer overwrite annotations on the Ambassador `service` when creating the Ambassador `deployment`

## [0.16.0] November 10, 2017
[0.16.0]: https://github.com/datawire/ambassador/compare/v0.15.0...v0.16.0

### Changed

- Support configuring Ambassador via `annotations` on Kubernetes `service`s
- No need for volume mounts! Ambassador can read configuration and TLS-certificate information directly from Kubernetes to simplify your Kubernetes YAML
- Expose more configuration elements for Envoy `route`s: `host_redirect`, `path_redirect`, `host_rewrite`, `auto_host_rewrite`, `case_sensitive`, `use_websocket`, `timeout_ms`, and `priority` get transparently copied

### Fixed

- Reenable support for gRPC

## [0.15.0] October 16, 2017
[0.15.0]: https://github.com/datawire/ambassador/compare/v0.14.2...v0.15.0

### Changed

- Allow `docker run` to start Ambassador with a simple default configuration for testing
- Support `host_rewrite` in mappings to force the HTTP `Host` header value for services that need it
- Support `envoy_override` in mappings for odd situations
- Allow asking the diagnostic service for JSON output rather than HTML

## [0.14.2] October 12, 2017
[0.14.2]: https://github.com/datawire/ambassador/compare/v0.14.0...v0.14.2

### Changed

- Allow the diagnostic service to show configuration errors.

## [0.14.0] October 5, 2017
[0.14.0]: https://github.com/datawire/ambassador/compare/v0.13.0...v0.14.0

### Changed

- Have a diagnostic service!
- Support `cert_required` in TLS config

## [0.13.0] September 25, 2017
[0.13.0]: https://github.com/datawire/ambassador/compare/v0.12.1...v0.13.0

### Changed

- Support using IP addresses for services.
- Check for collisions, so that trying to e.g. map the same prefix twice will report an error.
- Enable liveness and readiness probes, and have Kubernetes perform them by default.
- Document the presence of the template-override escape hatch.

## [0.12.1] September 22, 2017
[0.12.1]: https://github.com/datawire/ambassador/compare/v0.12.0...v0.12.1

### Changed

- Notify (in the logs) if a new version of Ambassador is available.

## [0.12.0] September 21, 2017
[0.12.0]: https://github.com/datawire/ambassador/compare/v0.11.2...v0.12.0

### Changed

- Support for non-default Kubernetes namespaces.
- Infrastructure for checking if a new version of Ambassador is available.

## [0.11.2] September 20, 2017
[0.11.2]: https://github.com/datawire/ambassador/compare/v0.11.1...v0.11.2

### Changed

- Better schema verification.

## [0.11.1] September 18, 2017
[0.11.1]: https://github.com/datawire/ambassador/compare/v0.11.0...v0.11.1

### Changed

- Do schema verification of input YAML files.

## [0.11.0] September 18, 2017
[0.11.0]: https://github.com/datawire/ambassador/compare/v0.10.14...v0.11.0

### Changed

- Declarative Ambassador! Configuration is now via YAML files rather than REST calls
- The `ambassador-store` service is no longer needed.

## [0.10.14] September 15, 2017
[0.10.14]: https://github.com/datawire/ambassador/compare/v0.10.13...v0.10.14

### Fixed

- Update `demo-qotm.yaml` with the correct image tag.

## [0.10.13] September 5, 2017
[0.10.13]: https://github.com/datawire/ambassador/compare/v0.10.12...v0.10.13

### Changed

- Properly support proxying all methods to an external authentication service, with headers intact, rather than moving request headers into the body of an HTTP POST.

## [0.10.12] August 2, 2017
[0.10.12]: https://github.com/datawire/ambassador/compare/v0.10.10...v0.10.12

### Changed

- Make TLS work with standard K8s TLS secrets, and completely ditch push-cert and push-cacert.

### Fixed

- Move Ambassador out from behind Envoy, so that you can use Ambassador to fix things if you completely botch your Envoy config.
- Let Ambassador keep running if Envoy totally chokes and dies, but make sure the pod dies if Ambassador loses access to its storage.

## [0.10.10] August 1, 2017
[0.10.10]: https://github.com/datawire/ambassador/compare/v0.10.7...v0.10.10

### Fixed

- Fix broken doc paths and simplify building as a developer. 0.10.8, 0.10.9, and 0.10.10 were all stops along the way to getting this done; hopefully we'll be able to reduce version churn from here on out.

## [0.10.7] July 25, 2017
[0.10.7]: https://github.com/datawire/ambassador/compare/v0.10.6...v0.10.7

### Changed
- More CI-build tweaks.

## [0.10.6] July 25, 2017
[0.10.6]: https://github.com/datawire/ambassador/compare/v0.10.5...v0.10.6

### Changed
- Fix automagic master build tagging

## [0.10.5] July 25, 2017
[0.10.5]: https://github.com/datawire/ambassador/compare/v0.10.1...v0.10.5

### Changed
- Many changes to the build process and versioning. In particular, CI no longer has to commit files.

## [0.10.1] July 3, 2017
[0.10.1]: https://github.com/datawire/ambassador/compare/v0.10.0...v0.10.1

### Added
- Changelog


## [0.10.0] June 30, 2017
[0.10.0]: https://github.com/datawire/ambassador/compare/v0.9.1...v0.10.0
[grpc-0.10.0]: https://github.com/datawire/ambassador/blob/v0.10.0/docs/user-guide/grpc.md

### Added
- Ambassador supports [GRPC services][grpc-0.10.0] (and other HTTP/2-only services) using the GRPC module

### Fixed
- Minor typo in Ambassador's `Dockerfile` that break some versions of Docker


## [0.9.1] June 28, 2017
[0.9.1]: https://github.com/datawire/ambassador/compare/v0.9.0...v0.9.1
[building-0.9.1]: https://github.com/datawire/ambassador/blob/v0.9.1/BUILDING.md

### Changed
- Made development a little easier by automating dev version numbers so that modified Docker images update in Kubernetes
- Updated [`BUILDING.md`][building-0.9.1]


## [0.9.0] June 23, 2017
[0.9.0]: https://github.com/datawire/ambassador/compare/v0.8.12...v0.9.0
[start-0.9.0]: https://github.com/datawire/ambassador/blob/v0.9.0/docs/user-guide/getting-started.md
[concepts-0.9.0]: https://github.com/datawire/ambassador/blob/v0.9.0/docs/user-guide/mappings.md

### Added
- Ambassador supports HTTP Basic Auth
- Ambassador now has the concept of _modules_ to enable and configure optional features such as auth
- Ambassador now has the concept of _consumers_ to represent end-users of mapped services
- Ambassador supports auth via an external auth server

Basic auth is covered in [Getting Started][start-0.9.0]. Learn about modules and consumers and see an example of external auth in [About Mappings, Modules, and Consumers][concepts-0.9.0].

### Changed
- State management (via Ambassador store) has been refactored
- Switched to [Ambassador-Envoy] for the base Docker image


## [0.8.12] June 07, 2017
[0.8.12]: https://github.com/datawire/ambassador/compare/v0.8.11...v0.8.12

### Added
- Mappings can now be updated


## [0.8.11] May 24, 2017
[0.8.11]: https://github.com/datawire/ambassador/compare/v0.8.10...v0.8.11
[istio-0.8.11]: https://github.com/datawire/ambassador/blob/v0.8.11/docs/user-guide/with-istio.md
[stats-0.8.11]: https://github.com/datawire/ambassador/blob/v0.8.11/docs/user-guide/statistics.md

### Added
- Ambassador interoperates with [Istio] -- see [Ambassador and Istio][istio-0.8.11]
- There is additional documentation for [statistics and monitoring][stats-0.8.11]

### Fixed
- Bug in mapping change detection
- Release machinery issues


## [0.8.6] May 05, 2017
[0.8.6]: https://github.com/datawire/ambassador/compare/v0.8.5...v0.8.6

### Added
- Ambassador releases are now performed by Travis CI


## [0.8.2] May 04, 2017
[0.8.2]: https://github.com/datawire/ambassador/compare/v0.8.1...v0.8.2

### Changed
- Documentation updates


## [0.8.0] May 02, 2017
[0.8.0]: https://github.com/datawire/ambassador/compare/v0.7.0...v0.8.0
[client-tls-0.8.0]: https://github.com/datawire/ambassador/blob/v0.8.0/README.md#using-tls-for-client-auth

### Added
- [Ambassador has a website!][Ambassador]
- Ambassador supports auth via [TLS client certificates][client-tls-0.8.0]
- There are some additional helper scripts in the `scripts` directory

### Changed
- Ambassador's admin interface is now on local port 8888 while mappings are available on port 80/443 depending on whether TLS is enabled
- Multiple instances of Ambassador talking to the same Ambassador Store pod will pick up each other's changes automatically


## [0.7.0] May 01, 2017
[0.7.0]: https://github.com/datawire/ambassador/compare/v0.6.0...v0.7.0
[start-0.7.0]: https://github.com/datawire/ambassador/blob/v0.7.0/README.md#mappings

### Added
- Ambassador can rewrite the request URL path prefix before forwarding the request to your service (covered in [Getting Started][start-0.7.0])
- Ambassador supports additional stats aggregators: Datadog, Grafana

### Changed
- _Services_ are now known as _mappings_
- Minikube is supported again


## [0.6.0] April 28, 2017
[0.6.0]: https://github.com/datawire/ambassador/compare/v0.5.2...v0.6.0

### Removed
- The Ambassador SDS has been removed; Ambassador routes to service names


## [0.5.2] April 26, 2017
[0.5.2]: https://github.com/datawire/ambassador/compare/v0.5.0...v0.5.2

### Added
- Ambassador includes a local `statsd` so that full stats from Envoy can be collected and pushed to a stats aggregator (Prometheus is supported)

### Changed
- It's easier to develop Ambassador thanks to improved build documentation and `Makefile` fixes


## [0.5.0] April 13, 2017
[0.5.0]: https://github.com/datawire/ambassador/compare/v0.4.0...v0.5.0

### Added
- Ambassador supports inbound TLS
- YAML for a demo user service is now included

### Changed
- The `geturl` script supports Minikube and handles AWS better
- Documentation and code cleanup


## [0.4.0] April 07, 2017
[0.4.0]: https://github.com/datawire/ambassador/compare/v0.3.3...v0.4.0

### Changed
- Ambassador now reconfigures Envoy automatically once changes have settled for five seconds
- Envoy stats and Ambassador stats are separate
- Mappings no longer require specifying the port as it is not needed

### Fixed
- SDS does the right thing with unnamed ports


## [0.3.1] April 06, 2017
[0.3.1]: https://github.com/datawire/ambassador/compare/v0.3.0...v0.3.1

### Added
- Envoy stats accessible through Ambassador
- Basic interpretation of cluster stats

### Changed
- Split up `ambassador.py` into multiple files
- Switch to a debug build of Envoy


## [0.1.9] April 03, 2017
[0.1.9]: https://github.com/datawire/ambassador/compare/v0.1.8...v0.1.9

### Changed
- Ambassador configuration on `/ambassador-config/` prefix rather than exposed on port 8001
- Updated to current Envoy and pinned the Envoy version
- Use Bumpversion for version management
- Conditionalized Docker push

### Fixed
- Ambassador keeps running with an empty services list (part 2)


## [0.1.5] March 31, 2017
[0.1.5]: https://github.com/datawire/ambassador/compare/v0.1.4...v0.1.5

### Fixed
- Ambassador SDS correctly handles ports


## [0.1.4] March 31, 2017
[0.1.4]: https://github.com/datawire/ambassador/compare/v0.1.3...v0.1.4

### Changed
- Ambassador keeps running with an empty services list
- Easier to run with [Telepresence]


## [0.1.3] March 31, 2017
[0.1.3]: https://github.com/datawire/ambassador/compare/82ed5e4...v0.1.3

### Added
- Initial Ambassador
- Ambassador service discovery service
- Documentation


Based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/). Ambassador follows [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

[Ambassador]: https://www.getambassador.io/
[Ambassador-Envoy]: https://github.com/datawire/ambassador-envoy
[Telepresence]: http://telepresence.io
[Istio]: https://istio.io/
