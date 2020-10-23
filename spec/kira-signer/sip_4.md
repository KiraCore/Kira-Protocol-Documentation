# [⏎](README.md#Roadmap) SIP_4
> Secret Data Transmission

It must be possible to transmit data in form of QR codes in bidirectional fashion from the online device to the offline device (HW) as well as from the offline device to the offline device (HW).

We have to create a self contained web, desktop, browser and mobile applications which can be used to read, write & transfer plaintext data in form of qr codes (single or multi-frame). The uncase is an ease of data transmission from offline devices to SAIFU, e.g. sharing keystores, PGP keys and other data between different devices.

The functionality must be simple and minimalist and fulfill two main goals:
1. user inputs text (write) -> one or many qr codes are generated
2. user scans one or many codes -> text is generated (read)

SAIFU app has to be be further modified to read & write arbitary data in/out from any of the self contained apps.

Dart & Flutter can be used for the mobile, web & desktop apps. In case of browser (OPTIONAL) we have to create a dedicated addon. 

SAIFU app can be extended to contain "encrypted store" functionality. So that any data can be saved under a used defined label and recovered & transmitted when needed. 