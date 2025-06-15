---------------------ArgoCD Basics & Installation--------------------





* Application A group of Kubernetes resources as defined by a manifest. This is a Custom Resource Definition (CRD).
* Application source type Which Tool is used to build the application.
* Target state The desired state of an application, as represented by files in a Git repository.
* Live state The live state of that application. What pods etc are deployed.
* Sync status Whether or not the live state matches the target state. Is the deployed application the same as Git says it should be?
* Sync The process of making an application move to its target state. E.g. by applying changes to a Kubernetes cluster.
* Sync operation status Whether or not a sync succeeded.
* Refresh Compare the latest code in Git with the live state. Figure out what is different.
* Health The health of the application, is it running correctly? Can it serve requests?
* Tool A tool to create manifests from a directory of files. E.g. Kustomize. See Application Source Type.
* Configuration management tool See Tool.
* Configuration management plugin A custom tool.


Getting Started With ArgoCD:
1. Install ArgoCD using commands:
   
   kubectl create namespace argocd
   kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


2. Port Forwarding
 
   kubectl port-forward svc/argocd-server -n argocd 8080:443



3. Login Using The CLI

    argocd admin initial-password -n argocd


