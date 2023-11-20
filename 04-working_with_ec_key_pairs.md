## UNDER CONSTRUCTION

Working with Elliptic Curve Key Pairs

Version 2.0.1, Section 6.1.5 Key Sizes, of the CA Browser Forums Baseline Requirements states "For ECDSA key pairs, the CA SHALL: Ensure that the key represents a valid point on the NIST P‐256, NIST P‐384 or NIST P‐521 elliptic curve. No other algorithms or key sizes are permitted." Therefore these are the only curves we will discuss. 
https://cabforum.org/wp-content/uploads/CA-Browser-Forum-BR-v2.0.1.pdf


<ol>
<li>Viewing all the Supported EC Curves, now which one to use ??? </li>
<br>
<code>openssl ecparam -list_curves</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

Note: In the below examples we need to pipe the ecparam module output to the ec module. This is because the ecparam module writes parameter data to STDOUT.  

<li>Create 256-bit Elliptic Curve Private Key</li>
<br>
<code>openssl ecparam -genkey -name prime256v1 | openssl ec -out ec-private.key</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>Create 384-bit Elliptic Curve Private Key</li>
<br>
<code>openssl ecparam -genkey -name secp384r1 | openssl ec -out ec-private.key</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>Create 521-bit Elliptic Curve Private Key</li>
<br>
<code>openssl ecparam -genkey -name secp521r1 | openssl ec -out ec-private.key</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>


Note: Compatible EC curves are listed below.  Others should be avoided unless otherwise noted. <br>
•	prime256v1: X9.62/SECG curve over a 256-bit prime field<br>
•	secp384r1 : NIST/SECG curve over a 384-bit prime field<br>
•	secp521r1 : NIST/SECG curve over a 521-bit prime field<br>



<li>Export the Elliptic Curve Public Key from the Private Key</li>
<br>
<code>openssl ec -in ec-private.key -outform PEM -pubout -out ec-public.key</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>Generating an Elliptic Curve Certificate Signing Request</li>
<br>
<code>openssl req -new -keyform PEM -key ec-private.key -out tims-mac.csr</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

<li>Evaluating a Certificate or a Certificate Signing Request</li>
<br>
<code>openssl req -in tims-mac.csr -text -noout</code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>


</ol>

