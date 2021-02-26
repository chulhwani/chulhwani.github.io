<strong>1. Kubernetes Cluster 생성</strong>
<p>&nbsp;</p>
<strong>2-1. Access Cluster(Cloud Shell Access)</strong>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>
<b># Cloud Shell 실행</b>
Welcome to Oracle Cloud Shell.

Your Cloud Shell machine comes with 5GB of storage for your home directory. Your Cloud Shell (machine and home directory) are located in: South Korea Central (Seoul).
Type `help` for more info.

chul_hwan_@cloudshell:~ (ap-seoul-1)$ oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.ap-seoul-1.aaaaaaaaae3dkmzxgi2gkndcgq2teyrrmfqtcm3emy2dkzjwmcygmnrwmfsd --file $HOME/.kube/config --region ap-seoul-1 --token-version 2.0.0 
New config written to the Kubeconfig file /home/chul_hwan_/.kube/config

<b># OKE Cluster 정보 확인</b>
chul_hwan_@cloudshell:~ (ap-seoul-1)$ kubectl cluster-info
Kubernetes master is running at https://192.29.29.118:6443
CoreDNS is running at https://192.29.29.118:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
</code></pre>
</div>
</div>
<p>&nbsp;</p>
<strong>2-2. Access Cluster(Local Access)</strong>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>
[root@docker-server ~]# id
uid=0(root) gid=0(root) groups=0(root) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023

[root@docker-server ~]# find / -name kubectl
/root/kubectl
/usr/local/bin/kubectl

[root@docker-server ~]# vi .bash_profile
PATH에 "/usr/local/bin" 추가
[root@docker-server ~]# . ./.bash_profile

[root@docker-server ~]# oci -v
2.21.2

[root@docker-server ~]# mkdir -p $HOME/.kube

[root@docker-server ~]# oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.ap-seoul-1.aaaaaaaaae3dkmzxgi2gkndcgq2teyrrmfqtcm3emy2dkzjwmcygmnrwmfsd --file $HOME/.kube/config --region ap-seoul-1 --token-version 2.0.0

<b># OKE Cluster 정보 확인</b>
[root@docker-server ~]# kubectl cluster-info
Kubernetes control plane is running at https://192.29.29.118:6443
CoreDNS is running at https://192.29.29.118:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
</code></pre>
</div>
</div>
