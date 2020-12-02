# Service-Discovery:

## Wie funktioniert Service-Discovery im allgemeinen?
Es gibt dabei zwei verschiedene Möglichkeiten. Zum einen ist es möglich, das sich innerhalb eines Service-Meshes die Services bzw. deren Sidecars direkt bei der Control-Plane. Zum anderen ist es auch möglich, dass es über ein Broadcast Request über das gesamte Netzwerk und ein spezielles Kommunikationsprotokol herauszufinden, welche Services vorhanden/erreichbar sind.

## Consul bzw. Consul Connect (von HashiCorp)
Meistens kommt ein Service-Mesh wie Consul bereits schon mit den Features von Service-Discovery. Dabei registiert sich der Proxy (Sidecar) des jeweiligen Services sich bei dem Control-Plane. Der Service ist dann automatisch unter einem Namen erreichbar.

Auch enthalten ist dann automatische Health-Checks, was es ermöglicht schnell darauf zu reagieren, wenn einer der Services nicht verfügbar ist.

Diese Service-Discoveries sind auch über mehrere Cloud-Plattformen, oder gar externen VMs, hinweg verfügbar.

Consul arbeitet wie jedes HashiCorp Produkt ideal mit Terraform zusammen. Damit ist es möglich die ganzen Netzwerk Themen automatisieren. Firewalls zwischen Services aufzusetzen, ist damit dann mit keinem manuellen Aufwand mehr verbunden.

### Quellen
- [Wo bist du? Consul: Service Discovery für den Microservice-Stack](https://www.innoq.com/de/articles/2016/12/devops-service-discovery-with-consul/)
- [Consul von HashiCorp](https://www.hashicorp.com/products/consul/multi-platform-service-mesh)