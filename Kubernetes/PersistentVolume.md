# Persistent Volumes

### Multi-attach Error

* This error can be cause once a node that has a PVC goes down.
* First we must change the Reclaim policy from Delete to Retain
```console
kubectl patch pv pv-name -p '{"spec":{"persistentVolumeReclaimPolicy":"Retain"}}'
 ```
* Now we can remove the claimSpec from the PV.
* Delete the previous PVC
* Run the command below to see the status of the PV
```console
kubectl get pv
```
* Now we can assign PersistentVolumeClaim to existing Persitent Volume 
under spec: volumeName: 
* Create a yml file and deploy it
```console
apiVersion: "v1"
kind: "PersistentVolumeClaim"
metadata:
  name: "claim1"
spec:
  accessModes:
    - "ReadWriteOnce"
  resources:
    requests:
      storage: "1Gi"
  volumeName: "pv0001"
```