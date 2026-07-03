# galaxy-test
Galaxy interview test 

- this repo included a pipeline to build the docker image and push to GitHub Container Registry (GHCR), which will be triggered on every push.
- the k8s-deploy.yml included all required k8s manifests:
    1. depoloyment using the image built by the pipleline above from the GHCR
    2. using a service at binding the app deployment on port 5000 to port 8080
    3. assumed the service will be published at https://galaxy-test.example.com:8080 which is declared in the ingress
    4. using a Horisontal Pod Autoscaler (HPA) to control the pods count for cost opptimisation 
