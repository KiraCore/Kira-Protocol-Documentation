# [⏎](README.md#Roadmap) SIP_2
>  PGP Signature

Create a Dart/Flutter application capable of a PGP signing a text message of the arbitrary length and extend previously created web application mocking the logic to propagate and verify signed message.

Main goal of this task is to showcase a simplest case of message signing and verification.

1. Allow user to define text an generate QR code gif containing that text
2. Enable mobile app to read all frames of the QR code
3. Sign the text embedded within QR code on the mobile device by the key initialized using standard [bip39 seed words](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) or in other words a [predictable, passphrase-derived PGP key](https://nullprogram.com/blog/2019/07/10/) ,
4. Generate QR code gif on the mobile device containing signed key and enable web-app to read it
5. Verify the signature on the web-app (web app must be made aware of the public key)

