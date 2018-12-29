## Openshift Important Commands

#### List out all projects
```oc get projects```

#### Select desired projects
```oc project my-project```

#### View all Services Display NAME,CLUSTER-IP,EXTERNAL-IP,PORT(S),AGE
```oc get svc```

#### Create new Project
```oc new-project my_project_name```

#### Delete  Project
```oc delete project my_project_name```

#### Delete Service
```oc delete service my-service-name```

### Create Config and Deploy Template file (Create pod using yaml)
```oc new-app -f D:/path/of/yaml/deploy.yaml --param SERVICE_VERSION="1.0.0" --param DOCKER_REGISTRY="docker-registry.xyz.svc:999/test```
