
Each of these examples can be tweaked to fit your purpose. 

Removing -out random.txt will put the text directly at the screen.
Modifying 1024 to a different number will create the specified amount of text in bits

## Generate 1024 bits of Base64 Encoded Text
<code>openssl rand -base64 -out random.txt 1024</code>

## Generate 1024 bits of Hex Encoded Text
<code>openssl rand -hex -out random.txt 1024</code>



