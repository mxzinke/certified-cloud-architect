# Service Meshes

m Gegensatz zu anderen Systemen der Kommunikationsverwaltung ist ein Service Mesh eine dedizierte, direkt in die App integrierte Infrastrukturschicht. Mit dieser lässt sich dokumentieren, wie gut (oder schlecht) die verschiedenen Komponenten einer App interagieren. Auf diese Weise wird die Kommunikation optimiert, und Ausfälle können minimiert werden, auch wenn die App immer größer wird.
Ein Service Mesh wird vorallem in einer Microservices Architektur verwendet. Mit wachsender Komplexität wird es schwerer Ausfälle zu diagnostizieren und auch muss die Kommunikation zwischen der Services entwickelt werden, was mit einem Service Mesh deutlich errleicht wird.

Kommunikation wird so über Sidecars geregelt. Diese Sidecars sind Module die vorgeschaltete Proxies darstellen. Diese ermöglichen vereinfachte Inter-Service Kommunikationen und der Service selbst muss keine Kommunikation implementieren (spricht nur mit dem Proxy). Diese Proxies werden oft auch als „Data Plane“ bezeichnet.

Da bei sehr vielen Services die Anzahl an Sidecars wächst, braucht man eine zentrale Stelle die die Konfiguration übernimmt. Diese Applikation nennt man „Control Plane“. Im Grund kommunizieren dann nur noch die Sidecars miteinander. So kann man auch Autorisierungen zwischen den Services festlegen oder ein Load-Balancing einrichten. Auch hilft es in Bereichen, wie zum Beispiel Tracing, um dem Entwicklern ein Tool an die Hand zu geben und somit zwischen hunderten Services den Fehler zu finden.
Produkte wie [Istio](https://istio.io) haben zudem noch viele andere Möglichkeiten/Features. Eines ist zum Beispiel, ein Teil des Traffics zum Staging Service umzuleiten.

### Quellen:
* [InnoQ - Service Meshes im Vergleich](https://www.innoq.com/de/articles/2020/10/service-meshes-im-vergleich/)
* [Redhat - Was ist ein Service-Mesh](https://www.redhat.com/de/topics/microservices/what-is-a-service-mesh)
* [servicemesh.es](https://servicemesh.es)