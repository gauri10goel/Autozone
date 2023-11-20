Coding Questions:
1. Write Kubernetes yaml file to deploy a sample app (You can use any publicly available app as
deployment image) & make sure: -
a. App is highly available.
b. App/Pods can be updated in rollout manner.


Solution: Refer the yaml file

  Execution: I have used Nginx as the sample app

The deployment YAML specifies the desired state for the sample app. It requests three replicas, which helps in achieving high availability. Adjust the replicas field based on your specific requirements.

The service YAML creates a ClusterIP service to expose the app internally within the cluster. You can change the type field to LoadBalancer or NodePort if you want external access.

To apply this YAML file, save it to a file (e.g., sample-app-deployment.yaml) and use the following command:
  kubectl apply -f sample-app-deployment.yaml
  

To update the app, you can change the image version in the Deployment YAML file or use the kubectl set image command. For example:
  kubectl set image deployment/sample-app sample-app=nginx:new-version
