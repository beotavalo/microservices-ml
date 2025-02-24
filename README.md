# Microservices for ML Projects
Tools and examples of microservices architecture for Machine Learning projects.
## Docker


## Kubernetes

1. Verify Kubernetes Cluster Context

Check if you are connected to a Kubernetes cluster:

```
kubectl config current-context
```

If this command outputs an error or shows no valid context, you are not connected to a cluster.
2. Set the Correct Kubernetes Context

Ensure that your kubectl is pointing to the correct cluster:

```
kubectl config use-context <your-context-name>
```

You can list all available contexts using:

```
kubectl config get-contexts
```

3. Ensure Your Cluster Is Running

If you're using a local Kubernetes cluster (like Minikube or Kind), ensure it is running:

Minikube:

```
minikube start
```

Kind:
```
kind create cluster
```
For cloud-based clusters (e.g., GKE, EKS, AKS), please ensure the cluster is up and running via your cloud provider's management console.
4. Check API Server Connection

Verify that kubectl can connect to the API server:
```
kubectl get nodes
```
If this command works, your connection to the cluster is fine.
5. Run the Apply Command Again

Once your cluster is running and connected, retry the command:
```
kubectl apply --dry-run=client -f first_manifest.yml
```
6. Temporary Workaround: Turn Off Validation

If you want to proceed without validation and are confident in your manifest file:
```
kubectl apply --validate=false -f first_manifest.yml
```
7. Common Causes of This Issue

API Server Not Running: Ensure the Kubernetes cluster is operational.
Incorrect Configuration: Your kubectl configuration may indicate a non-existent or inaccurate cluster.
Firewall or Network Issues: Ensure you can reach the Kubernetes API server from your machine.

8. Debugging Tips

If you still face issues, check the kubectl configuration:
```
kubectl config view
```
Please look over the clusters, contexts, and users sections for accuracy.


## References:
- [Is Microservice Architecture the best choice for Machine Learning Deployment?](https://towardsdatascience.com/is-microservice-architecture-the-best-choice-for-machine-learning-deployment-39ae325a2baf)
- [A Tale of Two Architectures](https://towardsdatascience.com/a-tale-of-two-architectures-48758462f5fd)
- [The Role of Microservices in ML](https://medium.com/mlops-community/the-role-of-microservices-in-ml-11f5bdd2a0b8)
- [Monolith vs micro: The $1M ML design decision](https://medium.com/@ayush.ranjan0503/microservices-vs-monolithic-architecture-572e73050e58)
- [Machine Learning in Production: Using Istio to Mesh Microservices in Google Kubernetes]( https://medium.com/retina-ai-health-inc/machine-learning-in-production-using-istio-to-mesh-microservices-in-google-kubernetes-engine-9b15fb643bab)
