# Pods
  - Take me to [Video Tutorial](https://kodekloud.com/topic/pods-2/)
  
In this section, we will take a look at PODS.
- POD introduction
- How to deploy pod?

#### Kubernetes doesn't deploy containers directly on the worker node , the containers are encapsulated in a Kubernetes object called Pod
     - Pod is the single instance of an application and the smallest unit u can create in K8s

  ![pod](../../images/pod.PNG)
  
#### Here is a single node kubernetes cluster with single instance of your application running in a single docker container encapsulated in the pod.

![pod1](../../images/pod1.PNG)

#### Pod will have a one-to-one relationship with containers running your application and if u need to scale anothe pod will be created and if
#### the node hasn't additional capacity a new node is created in the cluster . 

  ![pod2](../../images/pod2.PNG)
  
## Multi-Container PODs
- A single pod can have multiple containers except for the fact that they are usually not multiple containers of the **`same kind`**.
- the additional containers that can added to the pod are supporing the container in like processing some files , it lives along side to the contaienr
  , the two container can communicate with each others directly by refering to each others by localhost as they share the same namespace and they can share the same storage
  as well .
  
  ![pod3](../../images/pod3.PNG)
  
## Docker Example (Docker Link)
- in it we need to make all what the pod make but manually where we create a helper for each container and link them with the container 
  and make a map between them
  
  ![pod4](../../images/pod4.PNG)
  
## How to deploy pods?
Lets now take a look to create a nginx pod using **`kubectl`**.

- To deploy a docker container by creating a POD , first it make the pod and deploy the docker container image in it 
  ```
  $ kubectl run nginx --image nginx
  ```

- To get the list of pods
  ```
  $ kubectl get pods
  ```

 ![kubectl](../../images/kubectl.PNG)

K8s Reference Docs:
- https://kubernetes.io/docs/concepts/workloads/pods/pod/
- https://kubernetes.io/docs/concepts/workloads/pods/pod-overview/
- https://kubernetes.io/docs/tutorials/kubernetes-basics/explore/explore-intro/


