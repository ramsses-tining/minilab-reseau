# minilab-reseau
Configuration VLAN, DHCP, NAT, WIFI, VoIP
```markdown
 MiniLab Réseaux – VLAN, DHCP, WIFI, NAT & VoIP  

 Auteur

- Nom : Tining
- Prénom : Ramsses

---

 Objectif du projet

Ce projet vise à concevoir et configurer un réseau d'entreprise simulé avec Cisco Packet Tracer, intégrant :

- La segmentation du réseau via des VLANs.
- L'attribution dynamique des adresses IP avec DHCP.
- Le routage inter-VLAN.
- La mise en place du NAT pour l'accès à Internet.
- L'intégration de la VoIP avec des téléphones IP.
- Connexion Wi-Fi : Les portables se connectent via l’SSID configuré

---

 Équipements utilisés

- Routeur principal : Cisco 1941
- Routeur R-cloud : Simule l'accès Internet
- Switchs PT : 3 unités
- Points d'accès Wi-Fi PT-AC : 3 unités
- PC fixes : 6 unités
- PC portables : 3 unités
- Téléphones IP Cisco 7960 : 3 unités
- Bridge-PT : 1 unité

---

 Plan d'adressage et VLANs

| VLAN | Usage           | Adresse réseau     | Plage DHCP                   |
|------|-----------------|--------------------|------------------------------|
| 1    | VoIP            | 192.168.0.0/24     | 192.168.0.10 - 192.168.0.50  |
| 10   | PC fixes        | 192.168.10.0/24    | 192.168.10.10 - 192.168.10.50|
| 20   | Wi-Fi           | 192.168.20.0/24    | 192.168.20.10 - 192.168.20.50|
| 30   | Administration  | 192.168.30.0/24    | 192.168.30.10 - 192.168.30.50|

---

 Configuration des équipements

 Routeur principal (Cisco 1941)

- Création des sous-interfaces pour chaque VLAN :
  - GigabitEthernet0/0.1 pour VLAN 1
  - GigabitEthernet0/0.10 pour VLAN 10
  - GigabitEthernet0/0.20 pour VLAN 20
  - GigabitEthernet0/0.30 pour VLAN 30
- Configuration des adresses IP correspondantes.
- Activation du routage inter-VLAN.
- Configuration du DHCP pour chaque VLAN.
- Mise en place du NAT pour permettre l'accès à Internet via le routeur R-cloud.

 Switchs PT

- Création des VLANs : 1, 10, 20, 30.
- Affectation des ports :
  - Ports 2-3 : VLAN 1 (VoIP)
  - Ports 4-5 : VLAN 10 (PC fixes)
  - Ports 6-7 : VLAN 20 (Wi-Fi)
  - Port 8 : VLAN 30 (Administration)
  - Ports 1 et 9 : Trunk pour liaison entre switches et vers le routeur.

 Routeur R-cloud

- Configuration d'une interface simulant l'accès Internet.
- Connexion via le Bridge-PT pour permettre la communication avec le routeur principal.

---

 Tests de connectivité
- Ping entre les PC : Tous les PC, qu'ils soient fixes ou portables, peuvent se pinguer mutuellement, confirmant le bon fonctionnement du routage inter-VLAN.
- Ping entre les téléphones IP : Les téléphones IP reçoivent automatiquement une adresse IP via DHCP et peuvent se pinguer entre eux.
- Accès Internet : Tous les équipements ont accès à Internet via le NAT configuré sur le routeur principal.
- Connexion Wi-Fi : Les portables se connectent via l’SSID configuré


---


 Conclusion

Ce projet m'a permis de mettre en pratique les concepts fondamentaux du réseautage, notamment la segmentation du réseau avec les VLANs, l'attribution dynamique des adresses IP, le routage inter-VLAN, la configuration du NAT pour l'accès Internet et l'intégration de la VoIP. Les tests de connectivité ont confirmé la réussite de la configuration.
