OpenSSL has modules for working with RSA keys, these modules are genrsa & rsa.  
These modules allow OpenSSL to generate new keys, examine existing keys, and generally 





<ol>
<li>Create a 4096 bit RSA Private Key without a Pass Phrase</li>
 This private key can be used for various cryptographic operations, including encryption, decryption, and digital signatures. Keys can be various lengths, common lenghts are 2048, 3072 and 4096. Keys can be generated using massive lenghts but these are not practical. OpenSSL will throw an informational error if you attempt to create a private key longer than 16,384 bits.  
<br>
<code>openssl genrsa -out rsa-private.key 4096</code>
<br><br>
<img src="/images/03-01-openssl-genrsa-out-rsa-private-key-WEB.png" alt="" width=600>
<br><br><br>

<li>Encrypt an Existing Private Key Using AES256</li>
Note the header, this header provides information about the type of key or data that follows.
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
This command reads the private key, extracts the public key information from it, and then writes the public key to a file in PEM format. The -pubout option tells OpenSSL to output the public key.
<br>
<code>openssl rsa -in rsa-enc-private.key -outform PEM -pubout -out rsa-public.key</code>
<br><br>
<img src="/images/03-04-openssl-rsa-priv-pub-key-WEB.png" alt="" width=600>
<br><br><br>

<li>Inspect the RSA Public Key</li>
If you have a separate public key file (e.g., rsa-public.key) that contains the RSA public key in PEM format, you can inspect it to find out the public key size, the modulus & exponent value. 
<br>
<code>openssl rsa -pubin -in rsa-public.key -noout -text</code>
<br><br>
<img src="/images/" alt="" width=600>
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



