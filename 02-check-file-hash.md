# Using OpenSSL to Check File Hashes

File hashes provide an authoritative method of validating a file received is ....Frequently providers will display file hashes so that after an end user downloads the file they are ablet to validate that the file has been successfully transferred. 

## Verify Files MD5 Hash
<code>openssl md5 filename.bin</code>

## Verify Files SHA512 Hash
<code>openssl sha512 filename.bin</code>


## Verify Files SHA256 Hash
<code>openssl sha256 filename.bin</code>


## Verify Files SHA1 Hash
<code>openssl sha1 filename.bin</code>


In this example I've downloaded an IOS image from cisco.com.  Cisco has calculated the file hash and provided it so when we download the file we can guarantee the file is the same. 

<img src="/images/01-cisco-file-hashes.png" alt="SSH Server Configuration Status" width=600>



