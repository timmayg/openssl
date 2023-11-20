## UNDER CONSTRUCTION

Working with Certificate Files


<ol>


<li>Generating an Certificate Signing Request</li>
Here we take an existing RSA private key (rsa-private.key) and create a new CSR (server-name.csr). An interactive process will generate the CSR. CSRs are commonly used to request digital certificates from a Certificate Authority (CA) to secure websites and services.
<br>
<code>openssl req -new -keyform PEM -key rsa-private.key -out server-name.csr</code>
<br><br>
<img src="/images/06-01-openssl-req-csr-WEB.png" alt="" width=600>
<br><br><br>


<li>Inspect a Certificate Signing Request File</li>
<br>
<code>openssl req -in server-name.csr -noout -text</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>


<li>Inspect a Certificate Signing Request from CLI</li>
<br>
<code>openssl req -noout -text -verify</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>View PEM Certificate encoded data right from a file </li>
<br>
<code>openssl x509 -noout -text -in my-server-cert.cer</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>View PEM Certificate encoded data right from command line </li>
<br>
<code>openssl x509 -noout -text</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>Convert a binary DER file to Base64 PEM file</li>
<br>
<code>openssl base64 -d -in certificate-file.der | openssl pkcs7 -inform DER -outform PEM -print_certs -out certificate-file.pem</code>
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

