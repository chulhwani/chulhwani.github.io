<p></p>
<p><strong>1. To Installation the CLI</strong></p>
<p>MacOS, Linux, and Unix</p>
<div class="language-plaintext highlighter-rouge">
<div class="highlight">
<pre class="highlight"><code>bash -c "$(curl -L <a class="vglnk" href="https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh" rel="nofollow">https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh</a>)"
</code></pre>
</div>
</div>
<p>설치가 시작되면 설치 경로를 입력하라고 나오는데, 기본 경로로 설치합니다. (계속해서 엔터)</p>
<p>&nbsp;</p>
<p><strong>2. OCI-CLI Setup</strong></p>
<p>$ su - root</p>
<p>$ oci setup config&nbsp; &nbsp; =&gt; /root/bin/oci setup config</p>
<p>위와 같이 실행하면 ~/.oci 디렉토리에 config 파일이 생성됩니다.</p>
<pre class="highlight"><code>[root@chulhwani ~]# /root/bin/oci setup config</p>
<p>&nbsp;&nbsp;&nbsp; This command provides a walkthrough of creating a valid CLI config file.</p>
<p>&nbsp;&nbsp;&nbsp; The following links explain where to find the information required by this</p>
<p>&nbsp;&nbsp;&nbsp; script:</p>
<p>&nbsp;</p>
<p>&nbsp;&nbsp;&nbsp; User OCID and Tenancy OCID:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://docs.us-phoenix-1.oraclecloud.com/Content/API/Concepts/apisigningkey.htm#Other</p>
<p>&nbsp;</p>
<p>&nbsp;&nbsp;&nbsp; Region:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://docs.us-phoenix-1.oraclecloud.com/Content/General/Concepts/regions.htm</p>
<p>&nbsp;</p>
<p>&nbsp;&nbsp;&nbsp; General config documentation:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://docs.us-phoenix-1.oraclecloud.com/Content/API/Concepts/sdkconfig.htm</p>
<p>&nbsp;</p>
<p>Enter a location for your config [/root/.oci/config]:</p>
<p>Enter a user OCID: <strong><span style="color: #fe0000;">ocid1.user.oc1..aaaaa----------------------k2kdj47itn3ploa</span></strong></p>
<p>Enter a tenancy OCID: <strong><span style="color: #fe0000;">ocid1.tenancy.oc1..aaaa-----------------------ymvxiq</span></strong></p>
<p>Enter a region (e.g. eu-frankfurt-1, uk-london-1, us-ashburn-1): <strong><span style="color: #fe0000;">ap-seoul-1</span></strong></p>
<p>Do you want to generate a new RSA key pair? (If you decline you will be asked to supply the path to an existing key.) [Y/n]: <strong><span style="color: #fe0000;">Y</span></strong></p>
<p>Enter a directory for your keys to be created [/root/.oci]:</p>
<p>Enter a name for your key [oci_api_key]:</p>
<p>Public key written to: /root/.oci/oci_api_key_public.pem</p>
<p>Enter a passphrase for your private key (empty for no passphrase):</p>
<p>Private key written to: /root/.oci/oci_api_key.pem</p>
<p>Fingerprint: c5:93:32:d6:db:e3:86:ff:d5:da:ce:72:11:47:e4:73</p>
<p>Config written to /root/.oci/config</p>
<p>&nbsp;</p>
<p>&nbsp;&nbsp;&nbsp; If you haven't already uploaded your public key through the console,</p>
<p>&nbsp;&nbsp;&nbsp; follow the instructions on the page linked below in the section 'How to</p>
<p>&nbsp;&nbsp;&nbsp; upload the public key':</p>
<p>&nbsp;</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://docs.ap-seoul-1.oraclecloud.com/Content/API/Concepts/apisigningkey.htm#How2</p>
</code></pre>
<p>아래와 같은 정보를 요구합니다.<br />1) User OCID<br />2) Tenancy OCID<br />3) Region (예: ap-seoul-1)<br />4) CLI를 위한 key pair 생성 여부<br />- "<span style="color: #fe0000;">Y</span>" 선택하면 자동으로 key pair 가 생성되며, public key는 OCI -&gt; IAM -&gt; User 에서 등록 해야 합니다.<br />- 생성된 public key 파일 명은 oci_api_key_public.pem</p>
<p>&nbsp;</p>
<p><strong>3. Verifying OCI-CLI</strong></p>
<table>
<tbody>
<tr>
<td width="697">
<p>[root@chulhwani ~]# /root/bin/oci os ns get</p>
<p>{<br />&nbsp; "data": "cnuwdlyf6mlc"<br />}</p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
