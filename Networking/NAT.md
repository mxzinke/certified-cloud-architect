# Understanding NAT

NAT meint "Network Address Translation", also das übersetzen bzw. umwandeln einer IP Adresse in die jeweils andere, um in einem privaten Netz (z.B. in einer [VPC](./VPC.md)) mehrere vorhandene Ressourcen oder Dienste zu erreichen und dabei nach außen als eine Einheit zu wirken. Dabei ist das große Ziel nur mit einer IP-Adresse auszukommen und so nur eine knapp verfügbare IPv4 Adresse in Gebrauch zu nehmen.

Zu dem wird durch das NAT Gateway die eigentlichen Ressourcen geschützt, da nur bestimmte Teile der VM oder ähnliches nach außen erreichbar sind. Außerdem gibt es weitere Ressourcen im privaten Netz, die teils überhaupt keinen Nutzen nach außen hätten und somit effektiv durch das private Netz und das Gateway versteckt werden können, das hat zu Folge das es keine Angriffspunkte gibt.

## Wie funktioniert es?

Im Grunde wird bei einem klassischen NAT Gateway ein einzelner Server genutzt um alle verfügbaren Services zu repräsentieren. Je nach Herkunft der Anfrage bzw. über welche ursprüngliche Domain, wird die Frage im internen System umgeleitet ("geroutet").

Bei einigen Cloud Anbietern ist es nicht möglich, da es die Gefahr von IP-Spoofing gibt. (IP-Spoofing bezeichnet in Computernetzen das Versenden von IP-Paketen mit gefälschter Absender-IP-Adresse. Dabei werden die Header gefälscht und so IP basierende Authentifizierung versucht zum umgehen.)

## Cloud NAT (Google)

Google bietet eine selbst skalierende und managed Instanz an, die für High Load und Bandwidth ausgelegt ist.

Diese kann man über die Console auf direktem Weg zusammen mit einem VPC anlegen.
