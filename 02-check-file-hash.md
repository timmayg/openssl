# Using OpenSSL to Check File Hashes

File hashes provide an authoritative method of validating a file received is ....Frequently providers will display file hashes so that after an end user downloads the file they are ablet to validate that the file has been successfully transferred. 



<ol>
In these examples Im using a test file from this link.
https://link.testfile.org/30MB


<li>Verify Files MD5 Hash</li>
<br>
<code>openssl md5 30MB-Testfile.Org.zip </code>
<br><br>
<img src="/images/02-01-openssl-md5-WEB.png" alt="" width=600>
<br><br><br>


<li>Verify Files SHA1 Hash</li>
<br>
<code>openssl sha1 30MB-Testfile.Org.zip </code>
<br><br>
<img src="/images/02-02-openssl-sha1-WEB.png" alt="" width=600>
<br><br><br>

<li>Verify Files SHA256 Hash</li>
<br>
<code>openssl sha256 30MB-Testfile.Org.zip </code>
<br><br>
<img src="/images/02-03-openssl-sha256-WEB.png" alt="" width=600>
<br><br><br>

<li>Verify Files SHA512 Hash</li>
<br>
<code>openssl sha512 30MB-Testfile.Org.zip </code>
<br><br>
<img src="/images/02-04-openssl-sha512-WEB.png" alt="" width=600>
<br><br><br>

</ol>

In this example I've downloaded an IOS image from cisco.com.  Cisco has calculated the file hash and provided it so when we download the file we can guarantee the file is the same. 

<img src="/images/02-05-cisco-file-hashes-WEB.png" alt="SSH Server Configuration Status" width=200>
