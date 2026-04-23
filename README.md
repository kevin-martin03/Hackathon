# Hackathon
ESGI Hackathon

## Description
Déploiement d'une stack de monitoring Prometheus, Grafana, Node_exporter, Alertmanager. </br>
Les services Prometheus, Grafana, Alertmanager et Node_exporter sont sur la VM de Monitoring.</br>
Les machines dans la section **"inventory/node_exporter"** sont les machines qui vont exposer leurs métrics.

## Pré-requis
- Avoir un laptop avec Ansible servant de Node_manager afin de gérer les déploiements.
- Avoir un utilisateur nommé *Ansible* sur toute les machines, le déploiement se feront via cette utilisateur.
- Créer une paire de clés RSA. Ajouter sa clé public dans **./ssh/authorized_keys** des VMs contenant l'utilisteur *Ansible*

## Installation
`ansible-playbook -i inventory playbook.yml -u ansible`

### Modification à faire
Des modifications sont susceptible d'être réalisé selon vos besoin.

#### Modification sur les Nodes.</br>
Si nécessaire, changer/ajouter les **"noms" et "adresses IP"** dans le fichier **"./inventory"**. Une boucle récupère directement les IPs et noms de machine dans la section \[node_exporter] du fichier **inventory** afin de déployer node_exporter.

#### Modifications des alertes
L'ajout/modification d'alertes se fait via le fichier de configuration alertrules.yml situé dans **"./roles/prometheus/files/alertrules.yml"**

### Grafana
Le template Node-Exporter-Full est importé par défaut. **ID : 1860**

### Alertmanager
Alertmanager envoie des alertes sur le discord en fonction de la criticité.</br>
- Le channel **"Warnings"** regroupe les alertes simple selon les alertes définies dans Prometheus.</br>
- Le channel **"Critical"** regroupe les alertes **CRITIQUE** selon les alertes définies dans **Prometheus**.</br>

