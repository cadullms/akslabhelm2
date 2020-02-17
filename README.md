# AKS Lab

In the lab we have instructions for Helm 2, but in the cloud shell we have Helm 3 installed, which does not work together.

Please do the following (it will install helm2 side-by-side with helm3):

```sh
cd ~
wget https://get.helm.sh/helm-v2.16.1-linux-amd64.tar.gz
tar -xzvf helm-v2.16.1-linux-amd64.tar.gz
alias helm2="~/linux-amd64/helm"
```

After that, simply use "helm2" instead of "helm"
