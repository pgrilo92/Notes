# Deployments

## Example File

* apiVersion will be apps/v1 for most deployments.
* You must specify the kind of pods you are creating. In this case Deployment
* Under metadata we will can put the name of the api 
* Under Spec we will be adding more labels so we can tie all the pods together for this API
* The spec under template will set what is inside the pods. This is were we can pull the docker image of the api you wish to use.

```console
apiVersion: apps/v1
kind: Deployment
metadata:
  name: api-name
spec:
  replicas: 2 # number of replicas
  selector:
    matchLabels:
      name: api-name
  template:
    metadata:
      labels: 
        name: api-name
        app: api-name
        tier: backend # or frontend
        role: server # what is your 
    spec:
      nodeSelector:
        doks.digitalocean.com/node-pool: api-pool # this is optional if you to select specific node pool
      volumes:
        - name: api-name-disk
      imagePullSecrets:
        - name: registry-persmissions
      containers:
        - image: registry-url
          imagePullPolicy: Always
          name: api-name
          resources: # resources needed for memory and cpu
            requests:
              memory: "250Mi"
              cpu: "250m"
            limits:
              memory: "512Mi"
              cpu: "500m"
          ports:
            -containerPort: 8080 # set port
          readinessProbe: # to check the health of container
            httpGet:
              path: /_health
              port: 8080
            initialDelaySeconds: 5
            timeoutSeconds: 1
          envFrom: # optional variables from a secrets file
            - secretRef:
              name: core-config
          env: optional setting some variables
            - name: SERVICE_NAME
              value: "api-name"
```