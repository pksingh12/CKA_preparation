# CKA Preparation

This repo is for basic info related to CKA.

## Basic Commands
```
1.kubectl get componentstatuses 
```
NAME                 STATUS    MESSAGE              ERROR
scheduler            Healthy   ok                   
etcd-0               Healthy   {"health": "true"}   
controller-manager   Healthy   ok  



* [controller-manager] - responsible for running various controllers that regulate
  behavior in the cluster: for example, ensuring that all of the replicas of a service
  are available and healthy.
* [scheduler] - responsible for placing different
  pods onto different nodes in the cluster.
* [etcd] - server is the storage for the cluster where all of the API objects are stored.

```
2.kubectl get nodes       
3.kubectl describe nodes node-1    
```

* [Kubernetes Proxy] - responsible for routing network traffic to load-balanced services in the Kubernetes cluster.   




### Common kubectl commands

1. Contexts

```
* kubectl config --kubeconfig=config-demo2 set-cluster kubernetes --server=https://172.17.0.54:6443 --insecure-skip-tls-verify   
* kubectl config --kubeconfig=config-demo2 set-credentials developer --username=dev --password=Test@123 
* kubectl config --kubeconfig=config-demo2 set-context dev-frontend --cluster=minikube --namespace=kube-system --user=developer    
* kubectl config view     
* kubectl config --kubeconfig=config-demo2 view --minify     
```

**KeyPoint 1 -** you can also view the kubernetes objects as raw JSON or YAML using the -o json or -o yaml flags, respectively.   
**Keypoint 2 -** A common option for manipulating the output of kubectl is to remove the headers, which is often useful when combining kubectl with Unix pipes (e.g., kubectl ... | awk ...). If you specify the --no-headers flag, kubectl will skip the headers at the top of the human-readable table.     
**KeyPoint 3 -** Another common task is extracting specific fields from the object. kubectl uses the JSONPath query language to select fields in the returned object.    
Ex. ```kubectl get pods my-pod -o jsonpath --template={.status.podIP}```    
For more  detailed information use below command   
```kubectl describe <resource-name> <object-name>```

2. Creating, Updating, and Destroying Kubernetes Objects    
```kubectl apply -f obj.yaml   
   kubectl delete -f obj.yaml
```


```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc

