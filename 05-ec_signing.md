## UNDER CONSTRUCTION

Creating an OpenSSL based Certificate Authority with Elliptic Curve Keys

Note: This is an extremely down and dirty CA. What else would you expect??? 

<ol>
<li>Create an Elliptic Curve Key</li>
<br>
<code>openssl ecparam -genkey -name secp384r1 | openssl ec -out ca-private.key</code>
<br><br>
<img src="/images/05/openssl-ecparam-genkey-ca-private-key-WEB.png" alt="" width=600>
<br><br><br>


<li>Create a Root Certificate for the CA</li>
This CA Certificate will be used to sign any Certificate Signing Requests. Thats it, OpenSSL is now a Certificate Authority and is able to sign CSRs! I told you this would be down and dirty! 
<br>
<code>openssl req -x509 -new --key ca-private.key -sha256 -days 1825 -out lab-ec-openssl-ca.pem</code>
<br><br>
<img src="/images/05/openssl-req-x509-new-ca-private-lab-ec-ca-WEB.png" alt="" width=600>
<br><br><br>


<li>Review the CA Certificate</li>
Certificate Authorities use Self Signed Certificates to sign Certificate Signing Requests. 
<br>
<code>openssl x509 -in lab-ec-openssl-ca.pem -noout -text</code>
<br><br>
<img src="/images/05/openssl-x509-in-lab-ec-ca-noout-text-WEB.png" alt="" width=600>
<br><br><br>


<li>Create an </li>
<br>
<code></code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>



<li>Create a Certificate Signing Request for a ficticious Website</li>
<br>
<code>openssl req -new -keyform PEM -key ec-384-private.key -out test-fqdn.timslab.fun-ec.csr</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>



<li>Sign a CSR</li>
<br>
<code>openssl x509 -req -in CERTIFICATE-SIGNING-REQUEST -CA tims-openssl-ca.pem -CAkey ca-private.key -out IDENTITY-CERT-NAME.CER -days 356 -sha256 -extfile theglens.net.ext</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>


<li></li>
<br>
<code></code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li></li>
<br>
<code></code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

</ol>




