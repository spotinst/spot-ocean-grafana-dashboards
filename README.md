# Spot Ocean Scaling and Cost Optimization Dashboard

This dashboard provides real-time insights into the scaling, cost, usage, and right-sizing activities managed by Spot Ocean within your Kubernetes cluster. It showcases metrics related to node provisioning, optimization, cost efficiency, and recovery operations. The visualizations help you understand how Spot Ocean dynamically manages Kubernetes cluster resources to ensure optimal performance, cost savings, and high availability. Key actions such as scale-ups, scale-downs, node replacements, and manual interventions are highlighted to give a comprehensive view of your cluster’s operational status and health.

It includes comprehensive data on compute, storage, and networking expenses, helping you monitor and optimize cloud spending. Visualizations highlight the cost distribution across different resource types and track usage patterns over time. This information empowers customers to make informed decisions about resource allocation, identify cost-saving opportunities, and ensure efficient utilization of cloud infrastructure. Additionally, the dashboard enables the evaluation of Ocean’s right-sizing capability, demonstrating how efficient resource adjustments contribute to cost reduction while maintaining optimal cluster performance.

## Introduction

Spot Ocean (https://spot.io/product/ocean/) manages the scaling of the Kubernetes data plane, and the data generated in the process can be valuable for monitoring your containerized environment. Using well-defined Prometheus metrics for monitoring Ocean helps you understand cluster scaling and debug any issues that may arise. In addition, you can build alerts based on the metrics to address issues in real-time and track important trends on a dashboard of different Ocean metrics.

Ocean maintains an official set of metrics, natively scrapable by Prometheus. This set of metrics helps build a 360-degree view of Ocean's actions while providing application-driven infrastructure.

## Variables

- **Datasource**: Select the cluster datasource in a Grafana installation with multiple datasources available.
- **Ocean Cluster ID**: Filter data only for the selected ID, suitable for datasources with data from several Ocean clusters.
- **Aggregation Interval**: Used to set a relative time in panels with aggregated data. The relative time will be shown on the panel title.

## Metrics

By monitoring the following key metrics, you can understand how Ocean scales.

### Current Status

![Current Status](https://github.com/user-attachments/assets/2775cc95-e271-43af-8080-eaa41927714c)

- Ocean controller status. Source: Ocean.
- Kubernetes cluster Nodes. Source: Kubernetes API server.
- Nodes managed by Ocean. Source: Ocean.
- Cluster resources utilization - coming soon.
- Cluster cost during the selected aggregation interval. Source: Ocean.
- Top 5 workloads with maximum cost during the selected aggregation interval. Source: Ocean.
- Cluster cost's potential savings suggested by the right-sizing feature. Source: Ocean.

### Scaling

![Scaling](https://github.com/user-attachments/assets/62ce91c7-29f1-4e7d-8054-4b4cda5d6694)

#### Overview

- Cluster nodes' allocatable resources (CPU, memory, GPU). Source: Ocean.
- Ocean cluster headroom allocatable resources (CPU, memory, GPU). Source: Ocean.
- Ocean cluster resources limit (CPU, memory). Source: Ocean.
- Ocean nodes breakdown by instance lifecycle and availability zone. Source: Ocean.
- Cluster nodes' allocatable resources breakdown by instance lifecycle and availability zone. Source: Ocean.

#### Nodes Managed by Ocean Metrics

- Ocean nodes count over time. Source: Ocean.
- Ocean nodes count by instance lifecycle and availability zone over time. Source: Ocean.
- Cluster nodes' allocatable resources count by instance lifecycle and availability zone over time. Source: Ocean.

#### Resources Utilization Metrics

- Cluster resources (CPU, memory, GPU) utilization over time - coming soon.

#### Pods Metrics

- Average time for Pod to become ready over time. Source: Kubernetes API server.
- Pods in Running state. Source: Kubernetes API server.

#### Scaling Activity Overview

![Scaling Activities](https://github.com/user-attachments/assets/b1ba9cde-7c17-4161-9a0b-04bc97f35c3a)

- Scaling up and down events summaries. Source: Ocean.
- Failed scaling up and down events summaries. Source: Ocean.

#### Ocean Controllers Metrics

- Ocean Kubernetes controller status over time. Source: Ocean.
- Ocean Kubernetes controllers pods over time. Source: Kubernetes API server.
- Ocean Kubernetes controllers memory consumption over time. Source: Kubernetes API server.
- Ocean metrics controllers memory consumption over time. Source: Kubernetes API server.

### Cost Metrics

![Cost Metrics](https://github.com/user-attachments/assets/7a301d7d-468e-409a-8b7c-d43d7d7e4456)

#### Overview

- Month-to-Date cluster cost. Source: Ocean.
- Average daily cluster cost during the selected aggregation interval. Source: Ocean.
- Cluster cost breakdown during the selected aggregation interval. Source: Ocean.
- Cluster cost over time during the selected aggregation interval vs previous period. Source: Ocean.

#### Compute and Storage Metrics

- Average cost per CPU during the selected aggregation interval. Source: Ocean.
- CPU by instance lifecycle breakdown during the selected aggregation interval. Source: Ocean.
- Cluster storage cost during the selected aggregation interval. Source: Ocean.
- Cluster storage cost breakdown during the selected aggregation interval. Source: Ocean.
- Cluster compute cost over time. Source: Ocean.
- Cluster storage cost over time. Source: Ocean.
- Cluster CPU usage over time. Source: Ocean.
- Cluster memory usage over time. Source: Ocean.

#### Network Metrics

![Network Metrics](https://github.com/user-attachments/assets/31230671-8baf-4fed-8177-4ccaabcd387f)

- Cluster network cost during the selected aggregation interval. Source: Ocean.
- Cluster network usage during the selected aggregation interval. Source: Ocean.
- Cluster network cost breakdown during the selected aggregation interval. Source: Ocean.
- Cluster Intra-AZ network usage over time. Source: Ocean.
- Cluster Inter-AZ network cost over time. Source: Ocean.
- Cluster Inter-AZ network usage over time. Source: Ocean.
- Cluster Internet network cost over time. Source: Ocean.
- Cluster Internet network usage over time. Source: Ocean.
- Cluster Inter-Region network cost over time. Source: Ocean.
- Cluster Inter-Region network usage over time. Source: Ocean.

### Right-Sizing

Ocean metrics are relevant to Ocean Prometheus Exporter for EKS, AKS, and GKE.

More information at https://docs.spot.io/ocean/tools-and-integrations/prometheus/

## Cluster Dependencies / Prerequisites

- Ocean controller. More information at https://docs.spot.io/ocean/overview-kubernetes
- Ocean network client. More information at https://docs.spot.io/ocean/tutorials/install-network-client-v2
- Ocean metric exporter. More information at https://docs.spot.io/ocean/tools-and-integrations/prometheus/scrape
- kube-state-metrics service.
- Prometheus server.

## Dashboard Installation

- Connect Grafana to Prometheus as a data source. 
- Import the Spot Ocean Scaling and Cost Optimization Dashboard into Grafana using the template link at https://grafana.com/grafana/dashboards/21768-spot-ocean-scaling-and-cost-optimization-dashboard/ or inserting the Grafana.com ID - 21768
- or download the dashboard json from the current repository and load it into your Grafana.

<img style="width:30%;" alt="Dashboard Installation" src="https://github.com/user-attachments/assets/e84f161c-655a-4897-8f8c-d9893f9dadac">

## Conclusion 

The Spot Ocean Scaling and Cost Optimization Dashboard is a powerful tool for understanding and optimizing your Kubernetes clusters. By leveraging Prometheus and Grafana, you can gain deep insights into how Spot Ocean manages your infrastructure, helping you make informed decisions that lead to better performance and cost savings. Whether you’re tracking scaling events, analyzing costs, or evaluating right-sizing adjustments, this dashboard provides the comprehensive data you need to maintain an efficient and high-performing Kubernetes environment. 


## Next Plans

- Complete utilizaiton metrics and add right-sizing graphs

