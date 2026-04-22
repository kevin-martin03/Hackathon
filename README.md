# Hackathon
ESGI Hackathon

## Description
Déploiement d'une stack de monitoring Prometheus, Grafana, Node_exporter, Alertmanager.

## Pré-requis
Avoirun laptop avec Ansible servant de Node_manager afin de gérer les déploiements

## Installation
ansible-playbook -i inventory playbook.yml -u ansible

### Modification à faire
Changer les "noms" et "adresses IP" dans le fichier "inventory"
Changer les targets dans le fichier de configuration Prometheus "prometheus/templates/prometheus.conf.j2"

