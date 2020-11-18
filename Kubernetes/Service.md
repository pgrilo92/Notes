# Service

```console
apiVersion: v1
kind: Service
metadata:
  name: api-name
spec:
  ports: # choose the port for the pods to be listening
  - port: 80
    protocol: TCP
    targetPort: 8080
  selector:
    app: api-name
  type: ClusterIP # this is internal you can choose load balancer or other types
```