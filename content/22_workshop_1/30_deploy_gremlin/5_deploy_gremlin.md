+++
title = "Deploy Gremlin"
chapter = true
weight = 07
+++

# Gremlin Deploy

After you have logged in, click the **Avatar** Icon on the top right, and click **“Team Settings"**:

![Gremlin Navigation to Team Settings](/images/gremlin/gremlin_people_team.png)

Select the “Configuration” tab:

![Gremlin Navigation to Configuration](/images/gremlin/gremlin_config.png)

Go ahead and copy your **Team ID**, and press **“Reset”** in **Secret Key.** Make sure to copy the Key. 

Head on over to your terminal and start helm:
```
helm init
```

Then add the repo for the Gremlin Helm chart:
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

____
{{% notice tip %}}
If Helm V2
{{% /notice %}}

{{% notice tip %}}
TODO: Do this on Cloud9 cause vim
{{% /notice %}}

Download the Gremlin configuration manifest by running the following:

```
wget https://k8s.gremlin.com/resources/gremlin-conf.yaml
```
Open the file and update the following:

+ Replace the following line with your **Team ID**: “YOUR TEAM ID GOES HERE”
+ Replace the following line with your **Team Secret**: “YOUR TEAM SECRET GOES HERE” 
+ Replace the following line with a string that you will use to identify your cluster: “YOUR UNIQUE CLUSTER NAME GOES HERE”

Apply the manifest with this command: `kubectl apply -f gremlin-conf.yaml`

Download and apply the gremlin client manifest for your Kubernetes cluster by running the following:
```
kubectl apply -f https://k8s.gremlin.com/resources/gremlin-client-secret.yaml
```

Download and apply the k8s client manifest by running:
```
kubectl apply -f https://k8s.gremlin.com/resources/gremlin-chao-secret.yaml
```
To verify your deployment of Gremlin, verify you see the ec2 instances on the [Gremlin Clients page.](https://app.gremlin.com/clients/infrastructure)