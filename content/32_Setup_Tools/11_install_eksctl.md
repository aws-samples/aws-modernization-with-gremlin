+++
title = "4.1 Install eksctl"
chapter = false
weight = 11

+++

First, you will need ot install eksctl. [eksctl.io](https://eksctl.io/introduction/#installation). eksctl (pronounced "eks control") is a simple CLI tool for creating clusters on EKS. It is written in Go, uses CloudFormation, was created by [Weaveworks](https://weave.works) and it welcomes contributions from the community. 

At the terminal command prompt, enter the following two commands:

```
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
```

```
sudo mv /tmp/eksctl /usr/local/bin
```

This will install `eksctl` in your **Cloud9** environment. To test to make sure the command is installed properly, execute the command:

```
eksctl get cluster
```

You should see "No clusters found". You can also verify it was installed by checking the version:

```
eksctl version
```

For the current workshops, we will be using `eksctl` **0.19-rc.1** or newer. Please verify the version, as some features are only available in the **0.19** version of `eksctl`
