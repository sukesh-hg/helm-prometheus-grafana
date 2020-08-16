# helm-prometheus-grafana
Application performance management using popular open source tools like Prometheus and Grafana. This is my attempt at making an easy to deploy, easy to understand helm chart as I have always found the ones available on charts/stable repositiories a little overwhelming.

What this repository contains:
- Helm chart for Prometheus, complete with PVC, Secrets and a configurable prometheus.yml file
- Helm chart for Grafana, complete with PVC, Secrets and configurable grafana-conf.yaml and grafana-datasource.yaml files
- Helm chart for Postresql prometheus exporter, with configurable datasources
- Extra resource templates for managing Ingress and Backend Config for Google Cloud Platform
- Grafana dashboard templates for monitoring Server metrics, JVM metrics and Postgresql database

Dependencies:
- Kubernetes cluster with access to create Objects, Service accounts and RBAC roles
- Helm installed on the Kubernetes cluster (preferable latest versions)
- Postgresql setup with Admin user, if you are using postgres exporter with grafana dashboard

How to use this repo:\
You can install the entire setup at one go which would create Prometheus and Grafana with all the datasource and dashboards on your Kubernetes cluster.
Or you can pick and choose the components needed as per your use case merits.

To go for the complete package, simply clone this repo, cd to this repo and run 'helm install name -f values.yaml . -n namespace'\
To setup individual components, cd to the component path in charts and run the same command.
