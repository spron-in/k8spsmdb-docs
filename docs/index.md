# Percona Operator for MongoDB

The [Percona Operator for MongoDB](https://github.com/percona/percona-server-mongodb-operator) automates the creation, modification, or deletion of items in your Percona Server for MongoDB environment. The Operator contains the necessary Kubernetes settings to maintain a consistent Percona Server for MongoDB instance.

The Percona Kubernetes Operators are based on best practices for the configuration of a Percona Server for MongoDB replica set. The Operator provides many benefits but saving time, a consistent environment are the most important.

# Requirements

* [System Requirements](System-Requirements.md)

* [Design and architecture](architecture.md)

* [Comparison with other solutions](compare.md)

# Quickstart guides

* [Install with Helm](helm.md)

* [Install on Minikube](minikube.md)

# Advanced installation guides

* [Install on Google Kubernetes Engine (GKE)](gke.md)

* [Install on Amazon Elastic Kubernetes Service (AWS EKS)](eks.md)

* [Install on Microsoft Azure Kubernetes Service (AKS)](aks.md)

* [Generic Kubernetes installation](kubernetes.md)

* [Install on OpenShift](openshift.md)

* [Use private registry](custom-registry.md)

# Configuration

* [Application and system users](users.md)

* [Changing MongoDB options](options.md)

* [Anti-affinity and tolerations](constraints.md)

* [Exposing the cluster](expose.md)

* [Local storage support](storage.md)

* [Arbiter and non-voting nodes](arbiter.md)

* [MongoDB sharding](sharding.md)

* [Transport encryption (TLS/SSL)](TLS.md)

* [Data at rest encryption](encryption.md)

* [Telemetry](telemetry.md)

# Management

* [Backup and restore](backups.md)

* [Upgrade MongoDB and the Operator](update.md)

* [Horizontal and vertical scaling](scaling.md)

* [Multi-cluster and multi-region deployment](replication.md)

* [Monitor with Percona Monitoring and Management (PMM)](monitoring.md)

* [Add sidecar containers](sidecar.md)

* [Restart or pause the cluster](pause.md)

* [Debug and troubleshoot](debug.md)

# HOWTOs

* [OpenLDAP integration](ldap.md)

* [Creating a private S3-compatible cloud for backups](private.md)

* [Install Percona Server for MongoDB in multi-namespace (cluster-wide) mode](cluster-wide.md)

# Reference

* [Custom Resource options](operator.md)

* [Percona certified images](images.md)

* [Operator API](api.md)

* [Frequently asked questions](faq.md)

* [Release notes](RN/index.md)
