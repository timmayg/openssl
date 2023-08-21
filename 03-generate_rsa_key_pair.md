OpenSSL has modules for working with RSA keys, these modules are genrsa & rsa.  
These modules allow OpenSSL to generate new keys, examine existing keys, and generally 





<ol>
<li>Create a 2048 bit RSA Private Key without a Pass Phrase</li>
<br>
<code>openssl genrsa -out rsa-private.key 2048</code>
<br><br>
<img src="/images/03-01-openssl-genrsa-out-rsa-private-key-WEB.png" alt="" width=600>
<br><br><br>

<li>Encrypt an Existing Private Key Using AES256</li>
<br>
<code>openssl rsa -aes256 -in rsa-private.key -out rsa-enc-private.key</code>
<br><br>
<img src="/images/03-02-openssl-encrypt-priv-key-WEB.png" alt="" width=600>
<br><br><br>

<li>Create a 2048 bit RSA Private Key that is encrypted with AES256</li>
<br>
<code>openssl genrsa -aes256 -out rsa-enc-private.key 2048</code>
<br><br>
<img src="/images/03-03-openssl-genrsa-encrypt-priv-key-WEB.png" alt="" width=600>
<br><br><br>

<li>Export the RSA Public key from the Private Key</li>
<br>
<code>openssl rsa -in rsa-enc-private.key -outform PEM -pubout -out rsa-public.key</code>
<br><br>
<img src="/images/03-04-openssl-rsa-priv-pub-key-WEB.png" alt="" width=600>
<br><br><br>

<li>Generating an RSA Certificate Signing Request</li>
<br>
<code>openssl req -new -keyform PEM -key rsa-private.key -out tims-mac.csr</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>


<li>Inspect a Private Key that is in a File</li>
<br>
<code>openssl rsa -text -noout</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>Inspect a Private Key from the Command Line</li>
<br>
<code>openssl rsa -in rsa-private.key -text -noout</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>



</ol>



