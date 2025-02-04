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
<img width="959" alt="image" src="https://github.com/user-attachments/assets/0f3860d6-0ea8-4d30-a864-a3901d05d9b0">




# open HubCluster 
-----------------------
```bash
** aws eks describe-cluster --name hub-cluster --region us-east-1 --query cluster.status
```

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
# To reveal the actual password:

If you want to view the admin password directly instead of editing the secret, you can use this command:

```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 --decode
```
# ArgoCd UI
-------------------------------------------

<img width="959" alt="Screenshot 2024-10-21 145825" src="https://github.com/user-attachments/assets/53100cf5-373c-4b1b-bde2-2bda674f12b3">


![Screenshot 2024-10-21 153016](https://github.com/user-attachments/assets/bf9b23c3-c554-437b-917b-9f44a6293a9b)

# Argocd CLI 
---------------------------------------------------
argocd login <ip-address-port>

argocd cluster add <context> --server <ip-address-port>






