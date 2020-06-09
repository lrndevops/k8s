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

    # Record the DNS name of the service.
