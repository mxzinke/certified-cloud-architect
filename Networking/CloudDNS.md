# Domain Name Server (kurz DNS)

## Cloud Native DNS (von Google)
[Hier findest du die Referenz Dokumentation.](https://cloud.google.com/dns/docs/best-practices-dns?hl=de)
Beim Cloud DNS geht es nicht darum die authoritären Zonen für offentlich erreichbar Domains bereitzustellen. Es geht hier um interne Referenzen, wobei man eine übergeordnete Haupt-Domain wählt, auf die sich in der Organistion geeinigt wurde.

*Folgende Benennungsmuster für lokale Unternehmensresourcen sind „Best Practise“:*
* **Getrennte Domainnamen für lokale Server und für Google Cloud:** z. B. http://corp.example.com für Ihre lokalen Server und http://gcp.example.com für alle Ressourcen in Google Cloud oder auch vollkommen getrennte Domainnamen wie http://example.com und example.cloud.
* **Die Google Cloud-Domain als Subdomain der Domain, die lokale Server enthält:** Bei Verwendung der Domain http://example.com kann die lokale Umgebung http://corp.example.com und Google Cloud die Subdomain http://gcp.corp.example.com nutzen. Dies ist ein gängiges Muster, wenn die meisten Ressourcen vor Ort verbleiben.
* **Die lokale Domain als Subdomain der Domain, die Google Cloud-Einträge enthält:** Für Unternehmen mit wenigen lokalen Ressourcen (Digital-Native Organistions). Hauptdomain direkt für die Google Cloud und Subdomain für lokale Ressourcen
* **Die gleiche Domain für Google Cloud und die lokale Umgebung:**  Wenn ein einziges autoritatives DNS-System verwendet wird, dann sind Hybrid-Einträge möglich, die sowohl auf lokale, als auch auf Cloud Resource zeigen.

Es stellt sich die Frage wie man die Ressourcen trennen möchte, woran man anhand der Entscheidung auch die Wahl trifft wo der autoritative DNS System sitzt. Dabei gibt es verschieden Möglichkeiten. So kann man die DNS Server doppelt halten, heißt das ein DNS im lokal Netz und in der Cloud ist und dennoch beide Ressourcen teilen und/oder Daten kommunizieren.

Die Wahl der Netzarchitektur und wie man sein VPC mit den lokalem Netzwerk verknüpft ist an der Stelle entscheidend. Mehr zu dem Thema in der [Referenzarchitekturen für das Hybrid-DNS](https://cloud.google.com/dns/docs/best-practices-dns?hl=de#reference_architectures_for_hybrid_dns) von der GC-Referenzdokumentation.

Verschiedene Zusatz-Services wie zum Beispiel [SkyDNS](https://github.com/skynetservices/skydns), hilft dabei die verfügbaren Ressourcen zu finden. Dabei verweise ich auf das [Service-Discovery](./Service-Discovery.md) Thema.

## Ein weitere non-native Möglichkeit: CoreDNS
Die Software CoreDNS ist ein in Golang geschriebener Service (auch als Docker-Container verfügbar), der Plugin basierende ist und man die mögliche Formate hat um DNS Einträge zu machen oder zu kopieren. Dabei werden auch Lösungen wie BIND9, Terraform, Route56 von AWS oder direkt an ein Kubernetes Cluster.

Das Angebot an Möglichkeiten, welches CoreDNS anbietet, zeichnet den Service aus um eine großes Anwendungsfeld zu haben.