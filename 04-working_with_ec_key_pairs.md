## UNDER CONSTRUCTION

Working with Elliptic Curve Key Pairs

Version 2.0.1, Section 6.1.5 Key Sizes, of the CA Browser Forums Baseline Requirements states "For ECDSA key pairs, the CA SHALL: Ensure that the key represents a valid point on the NIST P‐256, NIST P‐384 or NIST P‐521 elliptic curve. No other algorithms or key sizes are permitted." Therefore these are the only curves we will discuss. 
https://cabforum.org/wp-content/uploads/CA-Browser-Forum-BR-v2.0.1.pdf


EC Keys are much different than RSA Keys. EC Private Key files only contain a Private and a Public Key, thats it. No exponents, no prime numbers, etc.


<ol>
<li>Viewing all the Supported EC Curves, now which one to use ??? </li>
OpenSSL supports a lot of curves. We will stick with the curves that the CA Browser Forum suggests as they are the most commonly supported and very strong.  <br>
NIST P-256: OpenSSL Name: prime256v1<br>
NIST P-384: OpenSSL Name: secp384r1<br>
NIST P-521: OpenSSL Name: secp521r1<br>
<br>
<code>openssl ecparam -list_curves</code>
<br><br>
<img src="/images/04/openssl-ecparam-list-curves-WEB.png" alt="" width=600>
<br><br><br>


<li>Create 256-bit Elliptic Curve Private Key using NIST P-256</li>
In the examples where we create a key we need to pipe the ecparam module output to the ec module. This is because the ecparam module writes parameter data to STDOUT. The ec module will take that output and properly write it to a key. 
<br>
<code>openssl ecparam -genkey -name prime256v1 | openssl ec -out ec-256-private.key</code>
<br><br>
<img src="/images/04/openssl-ecparam-genkey-name-prime256v1-WEB.png" alt="" width=600>
<br><br><br>


<li>Create 384-bit Elliptic Curve Private Key using NIST P-384</li>
<br>
<code>openssl ecparam -genkey -name secp384r1 | openssl ec -out ec-384-private.key</code>
<br><br>
<img src="/images/04/openssl-ecparam-genkey-name-secp384r1-WEB.png" alt="" width=600>
<br><br><br>


<li>Create 521-bit Elliptic Curve Private Key using NIST P-521</li>
<br>
<code>openssl ecparam -genkey -name secp521r1 | openssl ec -out ec-521-private.key</code>
<br><br>
<img src="/images/04/openssl-ecparam-genkey-name-secp521r1-WEB.png" alt="" width=600>
<br><br><br>


<li>View the P-386 Private Key in Base64 Format</li>
<br>
<code>cat ec-384-private.key</code>
<br><br>
<img src="/images/04/cat-ec-384-private-key-WEB.png" alt="" width=600>
<br><br><br>


<li>View the P-386 Private Key with OpenSSL</li>
Notice that the EC Private Key only contains a Private Key and a Public Key. This is much different than an RSA Private Key. 
<br>
<code>openssl ec -in ec-384-private.key -noout -text</code>
<br><br>
<img src="/images/04/openssl-ec-in-ec-384-private-key-WEB.png" alt="" width=600>
<br><br><br>


<li>Export the Elliptic Curve Public Key from the Private Key</li>
<br>
<code>openssl ec -in ec-384-private.key -outform PEM -pubout -out ec-384-public.key</code>
<br><br>
<img src="/images/04/openssl-ec-in-private.key-pubout-out-public-key-WEB.png" alt="" width=600>
<br><br><br>


<li>View the Exported P-386 Public Key with OpenSSL</li>
Notice that the Public Key that we have exported is exactly the same as we saw it in the Private Key. 
<br>
<code>openssl ec -in ec-384-public.key -pubin -noout -text</code>
<br><br>
<img src="/images/04/openssl-ec-in-public.key-pubin-noout-text-WEB.png" alt="" width=600>
<br><br><br>


<li>Generating an Elliptic Curve Certificate Signing Request</li>
<br>
<code>openssl req -new -keyform PEM -key ec-384-private.key -out test-fqdn.timslab.fun-ec.csr</code>
<br><br>
<img src="/images/04/openssl-req-new-out-ec-csr-WEB.png" alt="" width=600>
<br><br><br>


<li>Evaluating a Certificate or a Certificate Signing Request</li>
<br>
<code>openssl req -in test-fqdn.timslab.fun-ec.csr -text -noout</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>


</ol>

