# Basic Docker and Kub example

Docker Image: docker.io/voicest/api:v0.1.0

	kubectl apply -f deployment.yaml
 	kubectl get pod
	kubectl port-forward <pod id> 8888:80

The api will run on http://localhost:8888


