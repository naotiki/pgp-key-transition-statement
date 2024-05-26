# Key Transition Statement

Date: 2024/05/26

I have recently set up a new OpenPGP key,
and will be transitioning away from my old one.

The old key will continue to be valid for some time, but I prefer all
future correspondence to come to the new one. I would also like this
new key to be re-integrated into the web of trust.  This message is
signed by both keys to certify the transition.

The old key was:

```
pub   rsa4096 2022-05-02
      0F74 F731 5F75 8ABC A756  81E9 DC02 02C8 E7EA E191
```

And the new key is:

```
pub   nistp521 2024-05-26
      E6FB D0BF DB69 CCCE BDDD  7719 8A98 69D6 C111 24B6
```

To fetch the full key from a public key server, you can simply do:

```
gpg --keyserver keys.openpgp.org --recv-key 'E6FBD0BFDB69CCCEBDDD77198A9869D6C11124B6'
```

If you already know my old key, you can now verify that the new key is
signed by the old one:

```
gpg --check-sigs 'E6FBD0BFDB69CCCEBDDD77198A9869D6C11124B6'
```

If you don't already know my old key, or you just want to be double
extra paranoid, you can check the fingerprint against the one above:

```
gpg --fingerprint 'E6FBD0BFDB69CCCEBDDD77198A9869D6C11124B6'
```

If you are satisfied that you've got the right key, and the UIDs match
what you expect, I'd appreciate it if you would sign my key. You can
do that by issuing the following command:

**
NOTE: if you have previously signed my key but did a local-only
signature (lsign), you will not want to issue the following, instead
you will want to use --lsign-key, and not send the signatures to the
keyserver
**

```
gpg --sign-key 'E6FBD0BFDB69CCCEBDDD77198A9869D6C11124B6'
```

I'd like to receive your signatures on my key. You can either send me
an e-mail with the new signatures (if you have a functional MTA on
your system):

```
gpg --export 'E6FBD0BFDB69CCCEBDDD77198A9869D6C11124B6' | gpg --encrypt -r 'E6FBD0BFDB69CCCEBDDD77198A9869D6C11124B6' --armor | mail -s 'OpenPGP Signatures' <naotiki@naotiki.me>
```

Please let me know if you have any questions, or problems, and sorry
for the inconvenience.

Naotiki

This document is based on [this](https://github.com/JJ1LFC/pgp-key-transition)