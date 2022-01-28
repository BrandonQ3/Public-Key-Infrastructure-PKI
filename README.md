# Public-Key-Infrastructure (PKI)
 System for the creation, storage, and distribution of digital certificates which are used to verify that a particular public key belongs to a certain entity.
 
 ## Topography 
![Topography PKI](https://user-images.githubusercontent.com/84944319/151466372-ee4d6c9b-b3dc-4d30-985e-280b5c71bfc2.jpg)

## How PKI relates to Public Key cryptography
Public key infrastructure is built to facilitate effective use of public key cryptography.

In public key cryptography, the (public) encryption and (private) decryption keys differ. The public keys are published and are used for encrypting messages so that only the holder of the private decryption key is able to decrypt and read the messages. Public key infrastructure acts to ensure that the published public keys are bound to authenticated parties who hold the relevant decryption key and therefore PKI ensures that nefarious keys or questionable entities may be identified as such (by their lack of certification).

Public Key Infrastructure enables confidence that the public key found for any entity does indeed belong to that entity and not an attacker. This trust that messages, information and data will reach the intended recipient (and only said recipient) safely is necessary for asymmetric cryptosystems to be used on public networks.

## PKI in everyday use
The role of PKI is most prominent when looking at websites and SSL certificates which are used to prove ownership of a private key as part of the HTTPS protocol for secure web browsing.

PKI is important for web browsing, data sharing in the internet of things (IoT), financial transaction verification, blockchain infrastructure for cryptocurrencies and bootstrapping secure messaging systems - as all of these applications require trust between the parties that they are sharing data with the intended party and can therefore expect that their website request / money / sensitive data / message will end up in the right place.
central to any PKI is the Certificate Authority (CA). A PKI may in fact be formed with many CAs as may be necessary to increase network capacity. We fill focus on the single CA case for simplicity but there is little difference in the multiple CA case. A certificate authority is a trusted entity that undertakes identity verification and issues digital certificates. Formally, the CA is responsible for issuing, revoking and publishing digital certificates.
The certificate authority has its own public keys that are used in the generation and verification of the digital certificates it issues. Certificates are standardized to be issued in X.509 format. Upon issuing a digital certificate the CA will use their private key to digitally sign it. A digital certificate is simply a quantity of digital data (usually the details of the certified party) that has been signed using cryptographic means. The X.509 format standardizes the information to include who the certificate was issued to and by whom it was issued. Further to this the issue and expiry dates as well as the plaintext that was signed (usually SHA hashes of the content) form part of the signed data. Verification is then undertaken simply by following the verification protocol for whichever digital signature algorithm was used for issuing the certificate.

## Certificate Management System
The management system by which certificates are published, suspended, renewed and revoked is known as a certificate management system. This system is maintained by the CA as a central database for reference upon receiving requests for certificate verification.

The private keys of users of the PKI are stored offline and only linked to the PKI when necessary. This enables clients to avoid keeping their private keys online where they are vulnerable to theft. Separating them from the network on different hardware which itself is encrypted enables greater security and limited exposure to risk. This notion has been expanded in the world of cryptocurrencies, where cold or offline storage is preferred over hot wallets which are always online, after several high profile thefts of various cryptocurrencies.

## The Certificate Class System
Verification of identity can be onerous and time consuming and often full verification is not needed for exchanging emails as what is desired is the ability to avoid fraudulent emails and imposters. However, some cases such as government communications will require heavy vetting and the time and expense of this is justified when dealing with national secrets. The need for differing levels of authentication has been solved through a certification leveling system. The typical levels are as below.

* Class 1: Certificates easily acquired by verifying an email address.
* Class 2: Requires additional personal information beyond an email address to be issued.
* Class 3: Checks upon the requestor’s identity must be carried out before certification at level 3.
* Class 4: Rigorous checks carried out. Level 4 is generally used by large financial institutions and governments.
Clearly class 4 requires more effort to attain and the greater difficulty in attaining one and rigour of the checks confers greater confidence in the holder of a class 4 certificate than of a class 1. This is why class 4 certificate holders are trusted with financial transactions whereas class 1 holders will only be trusted to send emails and class 2 to serve websites.
