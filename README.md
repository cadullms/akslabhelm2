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

# Some additional hints:

*	In "Connect to cluster" session: It is not `CLUSTERNAME=ignite-<id>` 
But rather `CLUSTERNAME=akscluster-<id>`
*	In the "Troubleshooting" section:
    * The lab instructions say to go to "Controllers" and then click "Live Logs". In fact the button now is "Live Data (Preview)".
    * To see the environment variables, the lab does not mention that we need to drill down from the controller to the individual container.
*	In "Policy" section misses "Click Create" after "Click Review and Create"
*	In "Scale Application" section
    *	it needs to be http not https in "az container create -g $RGNAME -n loadtest --image azch/loadtest --restart-policy Never -e SERVICE_ENDPOINT=https://<hostname order capture service>"
    *	Additionally, we might add "--no-wait" to be able to see the logs while the thing is running
    *	The HPA is already in place, because the instructions told us to apply everything in ignite-day2-aks/manifest/app, which includes the hpa.yaml
*	"Policy Compliance" section talks about "Enforce Internal Load Balancer", which we did not select before. The instructions requested "No privileged containers" and "Only allowed images"  to be selected.
*	In "Security Center" section, we cannot select our cluster, because it is too young to show up when we arrive at this point of the lab.
