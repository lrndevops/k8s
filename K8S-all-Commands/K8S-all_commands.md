# get all nodes from the k8s cluster
kubectl get nodes

# details abouts the nodes
    kubectl describe node <node name>

## DeamonSets
    # deamonSets type
    kind: Daemonset

    # assign the lable to node
    kubectl label node [node_name] disk=ssd

    # delete the deamon set pod
    kubectl delete pods [pod_name] -n kube-system

    # change label to spinnig 
    kubectl label node [node_name] disk=hdd --owerwrite

    # pick the label to choose for your deamonSet:
    kubectl get node [node_name] --show-labels

## Creating a Service and Discovering DNS Names in Kubernetes


    # Create an nginx deployment using the latest nginx image.

    kubectl run nginx --image=nginx
 
    # Verify the deployment has been created successfully.
    kubectl get deployments

    # Create a service from the nginx deployment created in the previous objective.
    kubectl expose deployment nginx --port 80 --type NodePort

    # Verify the service has been created successfully.
    kubectl get services

    # Create a pod that will allow you to perform the DNS query.
    busybox.yaml

    kubectl create -f busybox.yaml

    # Verify that the pod has been created successfully.
    kubectl get pods

    # Perform the DNS query to the service created in an earlier objective.
    kubectl exec busybox -- nslookup nginx

    # Record the DNS name of the service.
    <service-name>.default.svc.cluster.local



### Displaying Scheduler Events
    # Get the information about your scheduler pod events.
    kubectl describe pods [scheduler_pod_name] -n kube-system

    # View the events in your default namespace
    kubectl get events

    # View the events in your kube-system namespace:
    kubectl get event -n kube-system

    # Watch events as they are appearing in real time
    kubectl get events -w

    # View the logs from the scheduler pod:
    kubectl logs [kube_scheduler_pod_name] -n kube-system

    # The location of a systemd service scheduler pod.
    /var/log/kube-scheduler.log



### Deploying an Application, Rolling Updates, and Rollbacks
    # curl loop
    while curl; http://nodeIp:port; done

    # 


