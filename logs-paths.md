**Ways to get to logs on Azure**
1. You can go to kubernetes cluster logs via workloads/pods/
2. You can use dedicated logs services(azure services) like application insights and container insights.
3. Application insights and container insights will work only if these logs are configured to go there.
4. If they are configured, they are collected in the store called (log analytics workspace)

# AKS cluster
### via Kubernetes Resources
1. Kubernetes services/clusters/project-cluster/Kubernets resources/workloads/pod/
2. Kubernetes services/clusters/project-cluster/Kubernets resources/services and ingresses

### via Monitoring
1. Kubernetes services/clusters/project-cluster/Monitoring/Logs

# Application Insights
### via application insights on Azure
1. Application Insights/project-specific-insight/Monitoring/Logs

# Container Insights
### via containerInsights
1. ContainerInsights/Log Analytics workspace/Logs/Tables/Containers/containerlogV2


# Description
- **Container Insights**: Investigate its pods, containers and runtime environment  
- **Application Insights**: Investigate its requests, failures and performance  
- **Log Analytics**: Store and query collected logs and application telemetry  
- **Azure Monitor**: Bring the monitoring capabilities together  
