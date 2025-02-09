# Kafka in KRaft Mode on Kubernetes (AKS)

This repository contains the setup and deployment instructions for running **Kafka in KRaft Mode** on **Azure Kubernetes Service (AKS)** with **Kafdrop** integration for monitoring and management. KRaft mode eliminates the need for ZooKeeper, simplifying your Kafka architecture while providing high scalability and availability.

## Key Features

- **Kafka in KRaft Mode**: Kafka runs without ZooKeeper for more efficient and simpler cluster management.
- **StatefulSet Deployment**: Ensures data persistence and high availability by using Kubernetes StatefulSets and PersistentVolumes.
- **Multi-Replica & Multi-Partition Support**: Scalable Kafka deployment with multiple brokers and partitions.
- **Kafdrop Integration**: Provides a web-based GUI for monitoring Kafka brokers, topics, partitions, consumer groups, and real-time message inspection.

## Prerequisites

Before deploying Kafka in KRaft mode on AKS, ensure the following:

1. **Azure Kubernetes Service (AKS)** cluster is up and running.
2. **kubectl** installed and configured to interact with the AKS cluster.

## Deployment Steps

### 1. Deploy Kafka in KRaft Mode

The following Kubernetes manifest files will create a **StatefulSet** for Kafka with 3 replicas, ensuring high availability:

- **StatefulSet**: Configures Kafka brokers as stateful pods with persistent volumes.
- **ConfigMaps**: Stores Kafka configuration files specific to each pod.

#### Apply the Kafka StatefulSet

```bash
kubectl apply -f kafka-statefulset.yaml
