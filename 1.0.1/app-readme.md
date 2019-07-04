Windocks SQL proxy

The Windocks SQL proxy delivers Windows SQL Server containers with database clones to a Kubernetes cluster. The proxy delivers the following:
- Creates a Windows SQL Server container on a designated external machine that already has Windocks installed. This can run anywhere on any cloud or on-prem
- Clones terabyte sized SQL Server databases in seconds and delivers them to the container
- Proxies SQL traffic from the client applications (users, .Net apps, Sql Server Management Studio, NodeJs apps etc) to the Windocks container
- Enables the client applications to work on the cloned databases. Usually these are production database clones. 
- Deletes the Windocks SQL Server container when the SQL proxy pod / container is deleted

Pre-requisites
1. Windocks installed on a machine accessible to the Kubernetes cluster via IP
2. Kubernetes cluster and CLI with kubectl

Steps

create secret generic proxy-secrets --from-literal=WINDOCKS_REQUIRED_USERNAME='administrator' --from-literal=WINDOCKS_REQUIRED_PASSWORD='yourpassword' --from-literal=WINDOCKS_REQUIRED_CONTAINER_SAPASSWORD='sapasswordyouwantforcontainer'


helm install path/to/directory/containing/helm/chart
