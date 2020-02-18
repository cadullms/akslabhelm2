# AKS Lab

In the [AKS Day 2 operations lab](https://github.com/Azure/ignite-day2-aks) we have instructions for Helm 2, but in the cloud shell we have Helm 3 installed, which does not work with these instructions. Specifically, the server component tiller was removed in Helm 3, which causes the `helm init` command to fail, when it used as described in the lab instructions.

Please do the following (it will install helm2 side-by-side with helm3):

```sh
cd ~
wget https://get.helm.sh/helm-v2.16.1-linux-amd64.tar.gz
tar -xzvf helm-v2.16.1-linux-amd64.tar.gz
alias helm2="~/linux-amd64/helm"
```

After that, simply use "helm2" instead of "helm" in the lab.
