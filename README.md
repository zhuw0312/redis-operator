### Supported Features

Here the features which are supported by this operator:-

- Redis cluster and standalone mode setup
- Redis cluster failover and recovery
- Inbuilt monitoring with prometheus exporter
- Dynamic storage provisioning with pvc template
- Resources restrictions with k8s requests and limits
- Password/Password-less setup
- Node selector and affinity
- Priority class to manage setup priority
- SecurityContext to manipulate kernel parameters

# redis-operator
redis for k8s
# Add the helm chart
helm repo add ot-helm https://ot-container-kit.github.io/helm-charts/
# Deploy the redis-operator
helm upgrade redis-operator ot-helm/redis-operator --install --namespace redis-operator

# Create redis cluster setup
helm upgrade redis-cluster ot-helm/redis-cluster \
  --set redisCluster.clusterSize=3 --install \ 
  --namespace redis-operator

# Create redis standalone setup
helm upgrade redis ot-helm/redis \
  --install --namespace redis-operator

