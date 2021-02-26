<strong>1. Kubernetes Cluster 생성</strong>
<p>&nbsp;</p>
<strong>2. Access Cluster(Cloud Shell Access)</strong>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>
Welcome to Oracle Cloud Shell.

Your Cloud Shell machine comes with 5GB of storage for your home directory. Your Cloud Shell (machine and home directory) are located in: South Korea Central (Seoul).
Type `help` for more info.

chul_hwan_@cloudshell:~ (ap-seoul-1)$ oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.ap-seoul-1.aaaaaaaaae3dkmzxgi2gkndcgq2teyrrmfqtcm3emy2dkzjwmcygmnrwmfsd --file $HOME/.kube/config --region ap-seoul-1 --token-version 2.0.0 
New config written to the Kubeconfig file /home/chul_hwan_/.kube/config
chul_hwan_@cloudshell:~ (ap-seoul-1)$ kubectl cluster-info
Kubernetes master is running at https://192.29.29.118:6443
CoreDNS is running at https://192.29.29.118:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
chul_hwan_@cloudshell:~ (ap-seoul-1)$ 
</code></pre>
</div>
</div>
<p>&nbsp;</p>
