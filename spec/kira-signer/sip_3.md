# [⏎](README.md#Roadmap) SIP_3
>  Functional HW Signer

Create a functional (app-store release ready) web & mobile applications utilizing all the information and code learned in SIP_1 & SIP_2 to enable user address creation and 2 way communication between web and mobile for the purpose of cryptographically signing text of the arbitrary length.

## Mobile App Login

User must have ability to open the application by using either numeric only pin of length of max 10 characters or fingerprint scanner. 

Pin should be setup when application is open for the first time. Within application we have to create setting page where pin can be reset.

To setup or rest the pin user must input the pin at least twice to ensure no mistype happened. 

We also need to ensure that pin input is extremely fast and easy for the user, that means phone-dial like keypad should be present and readable the second app is opened and each keypad button should further contain letters just like on the typical ATM machine as certain people use letters to memorize the pin.

![picture 1](https://i.imgur.com/ancCQCa.png)  

## Account Management (Mobile)

User needs ability to create, manage and import accounts, as well as name the individual accounts and preview public addresses as text and in QR code form.

It must be possible to either import private key in 3 ways: as plaintext, keyfile or derive any possible key type from BIP 39 seed words that user either inputs or chooses to generate new random seed words.

_NOTE: We must be made ABSOLUTELY sure that randomly generated BIP 39 seed words by the mobile app are truly random, we should either use built-in TRNG or a Secure RNG algorithm_

In case where user chooses to generate random seed words - he needs ability to define their number as well as be informed that he needs to write those words down. After words are written down user must confirm the words by selecting them in ordered manner from the suggested list of shuffled words. There should also be a skip option. 

_NOTE: We must disable ability to make screenshoots during account setup process_

Once key is added user must specify the key type such as `PGP`, `Bech32`, `P2PKH`, `P2SH`, `Ethereum` or others. In some cases such as `Bech32` a prefix and derivation patch might be required to be specified by the user. At all times we must ensure that the process is as painless as possible for the user.

Once key type is defined user should see his public key and have ability to name the key using alphanumeric ASCII characters.

To preserve key files info on the disk a strong random password should be used - derived randomly using a has of Device ID and user defined pin as seed for the RNG function. Changing the pin should result in the re-encryption of all key files. Pin should never be stored on the device and to test it's correctness a small file with encrypted a random number should be used.

User must have ability to export each individual key separately in form of encrypted key file by specifying a strong ASCII password during export process. To import the account back user needs to select the file and provide password to decrypt it. Key files should preserve all information that user used to customize them such as friendly name and public address, but should never preserve original mnemonic (BIP 39 words) for the security reasons - as it is likely user might have used the same seed words to generate multiple different private key types.

### Example Key File Structure
```
{
    "ethvatar": "0xXXXXXXXXXXXXXXXXX", // hex avatar
    "pubkey": "kiraXXXXXXXXXXXXXXXXX", // public key
    "prvkey": "XXXXXXXXXXXXXXXXXXXXXX" // encrypted private key
}
```


## Web Login

Each named account/key should have an associated unique [ethvatar](https://github.com/gitcoinco/ethavatar) or other consistent graphical symbol derived from the public key. By pressing on the ethvatar or some other button user should have ability to copy the `public` key to his clipboard or displaying a QR code.

`ethvatar` should be a part of the public field in the exported key files.

It would be ideal to embed ethvatar within the QR code.

To simulate a real user experience a web app should have a login button after which user has ability to show QR code with the public key to the web app. 

## Signing & Verification

After "login" step is complected and web app has knowledge of the user public key, user must have ability to input in the web app any arbitrary text and display it as QR code. The first frame of the QR code should contain the public key, so that user does not have to guess which key to select in order to sign the message.

On the mobile app side user should have a generic "SIGN" button which would allow him to scan the QR code and generate signature.

After signature generation, turning it into another QR code and scanning on the web app - the signature should be verified and the web app display SUCCESS or FAILURE status.

_NOTE: Mobile app should only show the signature as QR code and do NOT attempt to show entire message that was signed_


## Integration Testing

For the SIP_3 purposes we will be using PGP. To test the functionality we should verify the signature and key import with the keybase.io/verify after importing private key (generated via keybase) into the mobile app.

