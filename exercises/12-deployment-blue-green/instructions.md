# Exercise 12

In this exercise, you will set up a blue-green Deployment scenario. You'll first create the initial (blue) Deployment and expose it will a Service. Later, you will create a second (green) Deployment and switch over traffic.

1. Create a Deployment named `nginx-blue` with 3 replicas. The Pod template of the Deployment should use container image `nginx:1.23.0` and assign the label `version=blue`.
2. Expose the Deployment with a Service of type `ClusterIP` named `nginx`. Map the incoming and outgoing port to 80. Select the Pod with label `version=blue`.
3. Run a temporary Pod with the container image `alpine/curl:3.14` to make a call against the Service using `curl`.
4. Create a second Deployment named `nginx-green` with 3 replicas. The Pod template of the Deployment should use container image `nginx:1.23.4` and assign the label `version=green`.
5. Change the Service's label selection so that traffic will be routed to the Pods controlled by the Deployment `nginx-green`.
6. Delete the Deployment named `nginx-blue`.
7. Run a temporary Pod with the container image `alpine/curl:3.14` to make a call against the Service.