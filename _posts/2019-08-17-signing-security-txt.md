---
title: Signing security.txt with GPG
author: Ondřej Führer
date: 2019-08-17 21:33:01 +0200
categories: [Blogging, Security, Quick Tip]
tags: []
pin: false
---
A quick article about how to sign your `security.txt` file.

## What is security.txt
`security.txt` is a proposed standard which allows websites to define security policies.
You can find all about it on <https://securitytxt.org/> website.

## How to sign security.txt file using GPG
My [security.txt](https://www.fuhrer.cz/.well-known/security.txt) is signed with my GPG key. 
Here are the steps to take. Precondition for signing the key is to have a GPG key pair. 
How to generate that could be find in my previous article: [How to create GPG key on MacOS]()

1. Create your `security.txt` file
    
    ```bash
    > cat .well-known/security.txt
    Contact: security@fuhrer.cz
    Preferred-Languages: en, cz
    Canonical: https://www.fuhrer.cz/.well-known/security.txt
    Encryption: https://www.fuhrer.cz/key.asc
    ```

2. Use clear-sign from gpg to sign your file

    ```bash
    > gpg —clear-sign —default-key security@fuhrer.cz .well-known/security.txt
    gpg: using “security@fuhrer.cz” as default secret key for signing 
    ```

3. Check the generated `security.txt.asc` file has correct structure

    ```bash
    > cat .well-known/security.txt.asc
    -----BEGIN PGP SIGNED MESSAGE-----
    Hash: SHA256
    
    Contact: security@fuhrer.cz
    Preferred-Languages: en, cz
    Canonical: https://www.fuhrer.cz/.well-known/security.txt
    Encryption: https://www.fuhrer.cz/key.asc
    -----BEGIN PGP SIGNATURE-----
    
    iQJHBAEBCAAxFiEEI2bT5b+OWevsHdyK3q/ON0XQpkgFAl9X3RYTHHNlY3VyaXR5
    QGZ1aHJlci5jegAKCRDer843RdCmSNk2D/9+jkwq77D9HAGlH524Sx6aWir9IcF7
    y9pinAkVKTrezkODXvL5dToaOmziHQz7HX0DqbvspYdwwG3NeADNM5vzOxG6ZrCL
    Pi0sQqBO9O9pdQrSHqvpAZPOBFEQ60tF0x91Q475EJN4yh4tfpMmTXkyL+9699s6
    p/rowHQV6NvXfI98CnpQ3+WwVntQsjHqG/VSXb8lO2WqWv+q5orrjeG5m0lIIDtK
    kKwZy1Ftzjxuvim7Td6UizQSDMGnPzC1yU1Xd2DpbWC5k1/7aSP+8vnPSDg0Hb4Y
    H91hkNbzbPuUSE3279bN/heI2rhusx09XI+ghzqrChtaCDLScWfeLAl7OpD9aOnS
    AOIT3rxvWoMUdmfuYrVPlNzgwijDeqOQHewSPwmKGiUDRzv5FwLej9fr899xyV3B
    vY+dzysF0y26kDVKCZ6jaP6wJn2+T0iZMxsXVz5Z2rx4GuThB3njrKcaer3GhRo8
    YToaiKb2bHTH/ohuVBnGRgKoDYGms5e0MUnvci+keFiwOGxeZQvcwkba8ggECtHy
    VveggVqCrLsnfGqRpBHYh9SJGTjePEyAKZLgqi/27YPmMOpWn3P08DhshV0G2fYA
    w4+nr2zO49r0qazBUuCKQ/pg/DwuNYUl9UfMc9Z7vfUH5pNJ4OMuId8+5pFE3U4u
    syt9MtKDLDooXA==
    =rRvF
    -----END PGP SIGNATURE-----
    ```

4. Replace the original file with the content of the signed file

    ```bash
    > mv -f .well-known/security.txt.asc .well-known/security.txt
    ```

5. Verify the signature of the file

    ```bash    
    > gpg ——verify .well-known/security.txt
    gpg: Signature made Tue Aug 27 21:35:50 2019 CEST
    gpg:                using RSA key XXXXXXXXXXXXXXXXXXXXX
    gpg:                issuer “security@fuhrer.cz”
    gpg: Good signature from “Ondrej Führer <security@fuhrer.cz>” [ultimate]
    ```

That’s it! Now your signed `security.txt` is ready to be published. 
