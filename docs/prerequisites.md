# Prerequisites

### Get Free Cloud Subscription

[Free AWS account](https://aws.amazon.com/free/)

[Free Azure account](https://azure.microsoft.com/free/?ref=microsoft.com&amp;utm_source=microsoft.com&amp;utm_medium=docs&amp;utm_campaign=visualstudio )

[Free Google account](https://cloud.google.com/free/)

### Generate SSH authentication keys

SSH authentication keys are strings of text that come in pairs, as a private and a public key. Public key is used for authentication on the server side while private key should stay protected with a user and shouldn't be shared.

Online key generators:

- [Online RSA Key Generator](http://travistidwell.com/jsencrypt/demo/)
- [New Zealand RSA Key Generator](http://www.csfieldguide.org.nz/en/interactives/rsa-key-generator/index.html)

Windows-based key generators with SSH clients:

- [PuTTYgen](https://www.ssh.com/ssh/putty/windows/puttygen) - comes with PuTTY
- [MobaKeyGen](https://mobaxterm.mobatek.net/) - comes with MobaXterm

If all else fails and you are in true desperation, here is a weak 1024-bit key pair:

**Public key:**

```
---- BEGIN SSH2 PUBLIC KEY ----
Comment: "rsa-key"
AAAAB3NzaC1yc2EAAAABJQAAAIEAz1HxeWCB4XwPp9fo6pF2wPFjgTAT3FBjDWoF
7XWbdoMAtVhaFTMT8dJwVAfAMcBsqV7s1yYdHchB+JyJRdI+rUhkCf9GsrwO3EK4
pD0bQRsaGikMBstnaCJEo7rYa2ZLryRtaIOYe3mXv/3bdISXpY4zobYPzzB6KtI/
wGrbTPU=
---- END SSH2 PUBLIC KEY ----
```

**Private key:**

```
-----BEGIN RSA PRIVATE KEY-----
MIICWgIBAAKBgQDPUfF5YIHhfA+n1+jqkXbA8WOBMBPcUGMNagXtdZt2gwC1WFoV
MxPx0nBUB8AxwGypXuzXJh0dyEH4nIlF0j6tSGQJ/0ayvA7cQrikPRtBGxoaKQwG
y2doIkSjuthrZkuvJG1og5h7eZe//dt0hJeljjOhtg/PMHoq0j/AattM9QIBJQKB
gAs03J7G8kOKKlwZgjYxYF101PI58zxXX0zVTG2zVILyUxC4quxjoDaVwOHylMRr
RCTUstsyfh1JGFKgrXllT37kE35B3MIIzoKxQcyWlP9o56NsERM2LBN7EdiSQ4Kn
41njjfD6lPEJ8DS4CSOkQHtmSOnWpQRv3W899vf4yxNlAkEA7bbqdvyQdmd0uNtA
21BGdL2KGpR45hckMqdv+kHEUHUtFbUTz5muDlCxJYaBpmxHiFIQ4OY40YQX3TfH
IpXrhwJBAN9Ef8XWHKK69bqcGoAGhZGfQL87qnsg24rTDS61tfPogxz2apg7YjNr
P4ur33+CcyGcqtI8xEl1iPqvDc2YeqMCQQCNWAEIen9o/z57wKManm8U+xPYc/Tb
1miM0kKUzSieityJcpYoaTcPbj/RH4tcCQfwMMvD/oKmFzDIuWGl3JnhAkA8V7PU
mruhmlBARd2mD5m4p5T1ahJmd5VIHV2CPvLn+ablO64bTlHkYizZpBLkMRgymQuS
xFC56Go16h9n/7JxAkAgGaYeYJNL6YAfpKu4AVyjyC+yQFn4COnK5k/Pl/4ZSXDF
LcyHEu4ZeD6YWwNTYzMsw/8WVEQI6g4L9lyX6bHx
-----END RSA PRIVATE KEY-----
```

### Install SSH client (optional)

Windows:

- [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
- [MobaXterm](https://mobaxterm.mobatek.net/)