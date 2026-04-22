# Hackathon
ESGI Hackathon

## Description
Déploiement d'une stack de monitoring Prometheus, Grafana, Node_exporter, Alertmanager. </br>
Les services Prometheus, Grafana, Alertmanager et Node_exporter sont sur la VM de Monitoring.</br>
Les machines dans la section **"inventory/node_exporter"** sont les machines qui vont exposer leurs métrics.

## Pré-requis
- Avoirun laptop avec Ansible servant de Node_manager afin de gérer les déploiements.
- Avoir un utilisateur nommé *Ansible* sur toute les machines, le déploiement se feront via cette utilisateur.

## Installation
`ansible-playbook -i inventory playbook.yml -u ansible`

### Modification à faire
Modification à faire en fonction des Nodes.</br>
Changer les **"noms" et "adresses IP"** dans le fichier "inventory" </br>
Changer les targets dans le fichier de configuration Prometheus **"prometheus/templates/prometheus.conf.j2"**

