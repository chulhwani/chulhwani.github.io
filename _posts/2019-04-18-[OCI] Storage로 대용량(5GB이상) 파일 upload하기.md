---
category: [ OCI ]
---

<p><strong>OCI Storage</strong><strong>로 대용량(5GB이상) 파일 upload</strong></p>
<p>&nbsp;</p>
<p><strong>oci os bucket get -ns skstoa2018 --bucket-name datapump</strong></p>
<table>
<tbody>
<tr>
<td width="697">
<p>[opc@datatransfer20180829 .oci]$ /root/bin/oci os bucket get -ns skstoa2018 --bucket-name datapump</p>
<p>{</p>
<p>&nbsp; "data": {</p>
<p>&nbsp;&nbsp;&nbsp; "compartment-id": "ocid1.tenancy.oc1..aaaaaaaanf7lk32tckxdyufa6ppqqvf435ymqnypxe3zwsfvv6wbpvymvxiq",</p>
<p>&nbsp;&nbsp;&nbsp; "created-by": "ocid1.saml2idp.oc1..aaaaaaaamhj2lhbpkexgztojhjjvequkuhsmwhiokyidu7nrrmzcw7clhbiq/chul-hwan.shim@oracle.com",</p>
<p>&nbsp;&nbsp;&nbsp; "defined-tags": {},</p>
<p>&nbsp;&nbsp;&nbsp; "etag": "c82746b1-fb01-43c7-b0f7-af75972a026d",</p>
<p>&nbsp;&nbsp;&nbsp; "freeform-tags": {},</p>
<p>&nbsp;&nbsp;&nbsp; "metadata": {},</p>
<p>&nbsp;&nbsp;&nbsp; "name": "datapump",</p>
<p>&nbsp;&nbsp;&nbsp; "namespace": "skstoa2018",</p>
<p>&nbsp;&nbsp;&nbsp; "public-access-type": "NoPublicAccess",</p>
<p>&nbsp;&nbsp;&nbsp; "storage-tier": "Standard",</p>
<p>&nbsp;&nbsp;&nbsp; "time-created": "2018-08-23T09:59:13.398000+00:00"</p>
<p>&nbsp; },</p>
<p>&nbsp; "etag": "c82746b1-fb01-43c7-b0f7-af75972a026d"</p>
<p>}</p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<p>&egrave; 대용량</p>
<p><strong>oci os object bulk-upload -ns skstoa2018 -bn adw_backup --src-dir /home/opc/datamig</strong></p>
<table>
<tbody>
<tr>
<td width="697">
<p>[opc@datatransfer20180829 datatransfer]$ /root/bin/oci os object bulk-upload -ns skstoa2018 -bn adw_backup --src-dir /home/opc/datamig</p>
<p>&nbsp;</p>
<p>Uploaded exp_tcomshop.dmp&nbsp; [####################################]&nbsp; 100%</p>
<p>{</p>
<p>&nbsp; "skipped-objects": [],</p>
<p>&nbsp; "upload-failures": {</p>
<p>&nbsp;&nbsp;&nbsp; "exp_tcomshop.dmp": "{'status': 404, 'message': u\"Either the bucket named 'exp_tcomshop.dmp' does not exist in the namespace 'skstoa2018' or you are not authorized to access it\", 'code': u'BucketNotFound', 'opc-request-id': 'f559f770-4f14-712c-a907-6e42f9219920'}"</p>
<p>&nbsp; },</p>
<p>&nbsp; "uploaded-objects": {}</p>
<p>}</p>
<p>[opc@datatransfer20180829 datatransfer]$ /root/bin/oci os object bulk-upload -ns skstoa2018 -bn datapump --src-dir /datatransfer</p>
<p>Uploaded exp_tcomshop.dmp&nbsp; [####################################]&nbsp; 100%</p>
<p>{</p>
<p>&nbsp; "skipped-objects": [],</p>
<p>&nbsp; "upload-failures": {},</p>
<p>&nbsp; "uploaded-objects": {</p>
<p>&nbsp;&nbsp;&nbsp; "exp_tcomshop.dmp": {</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "etag": "748C63F2F868494DE0530240C00A6EE5",</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "last-modified": "Wed, 29 Aug 2018 04:38:46 GMT",</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "opc-multipart-md5": "MCyRT/KQrzYVyNUIl1sDBA==-59"</p>
<p>&nbsp;&nbsp;&nbsp; }</p>
<p>&nbsp; }</p>
<p>}</p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
