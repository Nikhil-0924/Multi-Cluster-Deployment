# Multi-Cluster-Deployment
Deployment of Multi Cluster 

# prerequisites

kubectl – A command line tool for working with Kubernetes clusters. For more information, see Installing or updating kubectl. https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html

eksctl – A command line tool for working with EKS clusters that automates many individual tasks. For more information, see Installing or updating. https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html

AWS CLI – A command line tool for working with AWS services, including Amazon EKS. For more information, see Installing, updating, and uninstalling the AWS CLI https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html in the AWS Command Line Interface User Guide.

After installing the AWS CLI, I recommend that you also configure it. For more information, see Quick configuration with aws configure in the AWS Command Line Interface User Guide. https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html#cli-configure-quickstart-config

Argo CD CLI(Not the actual Argo CD Installation) - https://argo-cd.readthedocs.io/en/stable/cli_installation/#installation



# Eks-Creation

EKS Setup

EKS Clusters Creation
----------------------------------------------------------------------------------------------------------------
eksctl create cluster --name hub-cluster --region us-west-1

eksctl create cluster --name spoke-cluster-1 --region us-west-1

eksctl create cluster --name spoke-cluster-2 --region us-west-1

EKS Clusters Deletion
----------------------------------------------------------------------------------------------------
eksctl delete cluster --name hub-cluster --region us-west-1

eksctl delete cluster --name spoke-cluster-1 --region us-west-1

eksctl delete cluster --name spoke-cluster-2 --region us-west-1

# Aws Configure
---------------------------------------
AWS Access Key ID 

AWS Secret Access Key 

Default region name

Default output format 

# Resources Creation 
----------------------------------------------------------------
1.Nodes

2.Insatances

3.VPc

4.CloudFromation 

# Creating Cluster
--------------------------------
<img width="959" alt="image" src="https://github.com/user-attachments/assets/95388e7f-9046-4a62-9cbe-537a29dcfaa3">

# Creating Nodes
--------
<img width="959" alt="image" src="https://github.com/user-attachments/assets/6081fd25-ea67-4e7d-86de-ec97bd6a395d">


# Creating VPC
---------------------------

<img width="959" alt="image" src="https://github.com/user-attachments/assets/7424b241-2109-4bd1-ac0b-e3693461831f">

# Creating CloudFromation 
-----------------

<img width="959" alt="image" src="https://github.com/user-attachments/assets/7a70db0a-8db4-4ca1-99ae-adbbe8b60084">

# Creating Instances 
---------------- 
<img width="959" alt="image" src="https://github.com/user-attachments/assets/4db4122c-8e3e-489b-97c1-6383b03ba11a">




# open HubCluster 
-----------------------
```bash
1. kubectl config get-contexts
````
```bash
2. kubectl config use-context
```
```bash
3. kubectl config current-config 
```
  ```bash
4. Install Argocd
kubectl create namespace argocd

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

```
```bash
5. kubectl get cm -n argocd
```
```bash
6. kubectl edit configmap <     > -n argocd

(Inscure) 
```
```bash
7. kubectl describe deployement/argocd-server -n arogocd
```
```bash
8. kubectl edit deploy/argocd-server -n argocd
/insecure
```





