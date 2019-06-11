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

#### Delete Service/deploymentConfig/configmaps
```oc delete service/DeploymentConfig/configmaps my-service-name/MyDeploymentConfig/configmaps```

#### Delete all related to app
```oc delete all -l app=xyz-deployment-template
  oc delete all -l app=xyz-config-template
```


#### Create Config and Deploy Template file (Create pod using yaml)
```oc new-app -f D:/path/of/yaml/deploy.yaml --param SERVICE_VERSION="1.0.0" --param DOCKER_REGISTRY="docker-registry.xyz.svc:999/test```

#### Pass Parameter
```
oc new-app -f  yaml_file_path/deploy.yaml  --param PROJECT_NAME="my_project" --param DOCKER_REGISTRY="my docker registry"
```

#### Take Parameter from file
``` oc new-app -f D:/path/to/your/config/file/test.yaml  --param-file=D:/path/to/enviornemt/file/test-dev.env```

#### View current project status
``` oc status ```

#### Get all pod/templates/svc/configmaps/route
``` oc get pods/templates/svc/configmaps/route```

#### View all params of template
``` oc process template-name ```

#### List out all services
```
oc get svc
```

#### Describe Particular Service
```
oc describe svc svc_name     ///this will show service ip and all assocaited pod ip

Name:                   service_name
Namespace:              Project_name
Labels:                 app=service_name-deployment-template
                        project=Project_name
                        template=java-services-template
Type:                   NodePort
IP:                     Service_IP
Port:                   http    80/TCP
NodePort:               http    31816/TCP
Endpoints:              Pod ip
Session Affinity:       None
Events:                 <none>

```

#### Get all nodes 
```
oc get nodes     //List all nodes including master 
```
#### Get all pods with ip and node
```
oc get pod -o wide
```

#### List out all routes
```
oc get routes
```

#### List out services with end points
```
oc get ep
```

#### List out all image stream from all namespace
```
oc get is --all-namespaces
```

#### Get yaml file of Service
```
oc get svc service-name -o yaml
oc get svc service-name -o yaml --export=true >service-name-yaml.backup
```
#### View host file
`oc exec pod_name  -- cat /etc/hosts`
