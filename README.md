# Helm

### Create a new Helm chart
```bash
$ helm create <app-name>

eg: helm create myfirsthelmapp
```

`Chart.yaml` > this contains all the information about our helm chart.

`values.yaml` > default configuration for your helm chart.

`charts` directory > if your chart has any dependencies on other charts this's where you put them.

`templates` directory > k8s configuration files

### Deploy the application

- Once your configuration files (yaml files) ready inside the  `templates` directory, you can deploy your application using below commanmd.
```
# go to the root directory if you're inside the helm app.
$ helm install <some-release-name> <your-helm-app-name> -n <namespace>

eg: helm install myfirstrelease myfirsthelmapp -n helm
```

- check: `helm ls -n <namespace>`
- Check created pods: `kubectl get all`

- Ennable minikube tunnel: `minikube tunnel`

- Check connection: `curl localhost:80`


### Adding templates

```bash
helm upgrade firstrelease my-first-helm-app --values my-first-helm-app/values.yaml -n helm
```

