# EnergyWeb

### Scenario 2 ###

1.Recommendation as for the application environments (how many and why?) and how are they going to be separated 
--> We can deploy the application on AKS/EKS cluster. (Choosing AKS since I have more exposure on Azure).
    We can choose 3 environments here: Stage, Dev and prod.
    We need to have prod in a different cluster and we can divide the other 2 environments in another clusters in different namespaces.
    OR best if we can have all the environments in different clusters.

2. Which tooling will you use for CI/CD and why? How to ensure no downtime during deployments?
--> If we are using AKS , we can use Azure DevOps for CICD as has full integration with Azure services with minimum efforts. 
    We can deploy the application with zero downtime using deployment strategies like rolling update and blue/green deployment.

3. What are the additional tooling you need to supplement the application with to ensure it runs smoothly on production?
--> We can integrate Prometheus and Grafana in our kubenetes cluster to have advanced query results and user readability of the results. 
    We can integrate Azure AD for better user and permisison management.

4. Networking & dns-records management and networking protection rules
--> Choose the correct networking model for the cluster. 
    Also traffic distribution/routing using ingress controller.
    We can create explicit network policies as well to restrict traffice.
    Use Azure Services like WAF or security center to improve security.


5. Mechanisms to ensure reliability and scalability
--> Use scale set for underlying VMS.
    Set up thresholds for CPU and memory to maximize or minimize number of nodes.
    Use availabilty zones to pretect the data

5. Alerting :
Integrate Azure services like COntainer insights, Log analytic workspace and Azure Monitor to have detailed logs and information.
Additionally you can aslo enable Prometheus and Grafana monitoring.
