# ArgoCD App Of Apps Sample
This repository contains a sample application of App Of Apps pattern with ArgoCD. 

Check if kubernetes is up and running(It can take some time):
```kubectl cluster-info```

Clone the sample App Of Apps implementation to current directory:
```git clone https://github.com/a1tan/appofappssample.git```

Install the ArgoCD application:
```kubectl apply -k appofappssample/applications/argocd```

This will install ArgoCD controllers to argocd namespace.

Wait until all resources up and running(It can take some time):
```kubectl get pods -n argocd -w```

Apply the parent application definition:
```kubectl apply -k appofappssample/parentapplication```

Check if applications installed and synchronized:
```kubectl get application -n argocd -owide -w```


If you want to change settings of ArgoCD and watch auto sync operations, just take this code and push to your own repository.
After you follow the same steps with your own repository you can change ArgoCD setup by pushing changes.
Or you can add your own applications too.
