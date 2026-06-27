#Room Name -TRY HACK ME
##Objective
Find decryption key to decrypt the encrypted file on http://10.128.174:5004

##Tools Used
 - OpenSSL
 - Linux(Ubuntu)

##What i found
Fund a hardcoded SECRET_KEY in/static/js/decrypt.js. This is client side exposure
AES-128-ECB,no salt

##How i exploited it
Decrypted using openssl enc -d -aes-128-ecb -K <hex-key> -in encrypted.bin

##What i learned
Key hardcoded in client-side JS means anyone can view it, ECB mode (weakest AES mode)-patterns in plain text survive encryption, No salt means a password can easily be cracked.
These cryptograhic failures can make breach almost too easy for attackers 
