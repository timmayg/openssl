## UNDER CONSTRUCTION

Creating an OpenSSL based Certificate Authority with Elliptic Curve Keys

Note: This is an extremely down and dirty CA. What else would you expect??? 

<ol>
<li>Create an Elliptic Curve Key</li>
<br>
<code>openssl ecparam -genkey -name secp384r1 | openssl ec -out ca-private.key</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>Create a Root Certificate for the CA</li>
<br>
<code>openssl req -x509 -new --key ca-private.key -sha256 -days 1825 -out tims-openssl-ca.pem</code>
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




