
|                                                                       |                                                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How to select a hashing<br>algorithm                                  | Select a hashing algorithm without conflicts<br><br>SHA family                                                                                                                                                                                                                                    |
| Does Java SE has the <br>support for cryptography                     | Yes. javax.crypto is the library for cryptography <br> in java and it provides low level API<br><br>But low level knowledge is required for it.<br>Due to this reason a high level library is used<br>which created base on javax.crypto<br><br>`apache commons-codec`<br>`apache commons-crypto` |
| why `apache commons-codec`<br>and `apache commons-crypto`<br>used for | `apache commons-codec` -><br>Symmetric Encryption / Decryption <br>Asymmetric Encryption / Decryption<br><br>`apache commons-crypto`-><br>Hasing<br>Encoders / Decoders<br>                                                                                                                       |
|                                                                       |                                                                                                                                                                                                                                                                                                   |
How does the user registration works with has code
![[Pasted image 20240508200011.png]]

How does the login works with hash code

![[Pasted image 20240508202419.png]]


|                                                                             |                                |
| --------------------------------------------------------------------------- | ------------------------------ |
| What is the reason<br>to use secure channel                                 | prevent attack through network |
| What is the reason to<br>use hash code password<br>instead a plain password |                                |
