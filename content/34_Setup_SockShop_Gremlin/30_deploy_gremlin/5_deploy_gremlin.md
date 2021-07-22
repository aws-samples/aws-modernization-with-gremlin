+++
title = "5.3.2 Deploy Gremlin"
chapter = false
weight = 07
+++

Before you can run attacks, you must deploy the Gremlin agent to your environment. But first, you need to be able to authenticate the agent with your Gremlin account.

Let's find your credentials. Click the **Avatar** icon on the top right, then click **Team Settings**:

![Gremlin Navigation to Team Settings](/images/gremlin/gremlin_people_team.png)

Select the “Configuration” tab:

![Gremlin Navigation to Configuration](/images/gremlin/gremlin_config.png)

Here, you'll find your Team ID and Secret Key. You might need to generate a Secret Key if you haven't already (if you do have one set, click the Reset button to create a new one). Make sure to copy the key.

Next, open your terminal and run the following command to add the repo for the Gremlin Helm chart:
```
helm repo add gremlin https://helm.gremlin.com

```

**If you are running this workshop on your own**, create a namespace for the Gremlin Kubernetes client:
```
kubectl create namespace gremlin
```

Next, you will run the `helm` command to install the Gremlin client. In this command there are three placeholder variables that you will need to replace with real data. Replace `$GREMLIN_TEAM_ID` with your Team ID, and replace `$GREMLIN_TEAM_SECRET` with your Secret Key. You also want to replace `$GREMLIN_CLUSTER_ID` with a unique name for your cluster. This is the name that your cluster will appear as in the Gremlin web app.
```
    helm install gremlin gremlin/gremlin \
    --namespace gremlin \
    --set gremlin.secret.managed=true \
    --set gremlin.secret.type=secret \
    --set gremlin.secret.teamID=$GREMLIN_TEAM_ID \
    --set gremlin.secret.clusterID=$GREMLIN_CLUSTER_ID \
    --set gremlin.secret.teamSecret=$GREMLIN_TEAM_SECRET
```

Congrats! 🎉 You've deployed Gremlin to your cluster. Head over to the [Gremlin web app](https://app.gremlin.com/clients/infrastructure) to verify your installation.

![Gremlin Clients View](/images/gremlin/gremlin_ui_clients.png)
