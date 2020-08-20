+++
title = "Deploy Gremlin"
chapter = true
weight = 07
+++

# Gremlin Deploy

After you have logged in, click the People Icon on the top right, and click “Team Settings", followed by selecting thw “Configuration” tab. 

Go ahead and copy your Team ID, and press “Reset” in Secret Key. Make sure to copy the Key. 

Head on over to your terminal and add the repo for the Gremlin Helm chart:
```
helm repo add gremlin https://helm.gremlin.com

```
Create a namespace for the Gremlin Kubernetes client:
```
kubectl create namespace gremlin
```

Next, you will run the `helm` command to install the Gremlin client. In this command there are three placeholder variables that you will need to replace with real data. Replace `$GREMLIN_TEAM_ID` with your Team ID from earlier, and replace `$GREMLIN_TEAM_SECRET` with your Secret Key as well. You also want to replace `$GREMLIN_CLUSTER_ID` with a name for the cluster.
```
helm install gremlin/gremlin \
    --name gremlin \
    --namespace gremlin \
    --set gremlin.secret.managed=true \
    --set gremlin.secret.type=secret \
    --set gremlin.secret.teamID=$GREMLIN_TEAM_ID \
    --set gremlin.secret.clusterID=$GREMLIN_CLUSTER_ID \
    --set gremlin.secret.teamSecret=$GREMLIN_TEAM_SECRET
```

Congrats! 🎉 You've deployed Gremlin to your cluster. Head over to https://app.gremlin.com/clients/infrastructure to verify your installation on the Gremlin UI. 
