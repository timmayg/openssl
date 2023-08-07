
The OpenSSL rand module creates cryptographically secure random numbers. 

It is able to create base64 and hex digits, just tell it what you want it to do. 

<li>Generate 512 bits of Base64 Encoded Text to the screen</li>
<br>
<code>openssl rand -base64 512</code>
<br><br>
<img src="/images/01-01-openssl-rand-base64-512.png" alt="" width=600>
<br><br><br>




<li></li>
<br>
<code></code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

## Generate 512 bits of hex Encoded Text to the screen
<code>openssl rand -hex 512</code>
<img src="/images/01-02-openssl-rand-hex-512.png" alt="" width=600>

<li></li>
<br>
<code></code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

## Generate 512 bits of Base64 Encoded Text to a file
<code>openssl rand -base64 -out random.txt 512</code>
<img src="/images/" alt="" width=600>

<li></li>
<br>
<code></code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>

## Generate 512 bits of Hex Encoded Text to a file
<code>openssl rand -hex -out random.txt 512</code>
<img src="/images/" alt="" width=600>


<li></li>
<br>
<code></code>
<br><br>
<img src="/images/" alt="" width=600>
<br><br><br>
