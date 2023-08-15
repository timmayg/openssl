
The OpenSSL rand module creates cryptographically secure random numbers. 

It is able to create base64 and hex digits, just tell it what you want it to do. Here are a few examples I frequently use. 


<ol>
<li>Generate 512 bits of Base64 Encoded Text to the screen</li>
<br>
<code>openssl rand -base64 512</code>
<br><br>
<img src="/images/01-01-openssl-rand-base64-512-WEB.png" alt="" width=600>
<br><br><br>


<li>Generate 512 bits of hex Encoded Text to the screen</li>
<br>
<code>openssl rand -hex 512</code>
<br><br>
<img src="/images/01-02-openssl-rand-hex-512-WEB.png" alt="" width=600>
<br><br><br>


<li>Generate 512 bits of Base64 Encoded Text to a file</li>
<br>
<code>openssl rand -base64 -out random-b64.txt 512</code>
<br><br>
<img src="/images/01-03-openssl-rand-base64-out-512-WEB.png" alt="" width=600>
<br><br><br>


<li>Generate 512 bits of Hex Encoded Text to a file</li>
<br>
<code>openssl rand -hex -out random-hex.txt 512</code>
<br><br>
<img src="/images/01-04-openssl-rand-hex-out-512-WEB.png" alt="" width=600>
<br><br><br>


