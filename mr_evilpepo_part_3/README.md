# Description

The Top Secret file of Mr.EvilPepo is still not discovered this is your last mission of finding the top secret file related to Mr.EvilPepo Good Luck

Note: Use the file provided in Mr.EvilPepo Part-1

## Solution

Now let's see pslist and we can see notepad.exe was opened

`python2 vol.py --plugins=volatility-plugins/ -f ~/my_challenges/evilpepo.vmem --profile Win7SP1x64 pslist`

ok let's check clipboard too.

`python2 vol.py --plugins=volatility-plugins/ -f ~/my_challenges/evilpepo.vmem --profile Win7SP1x64 clipboard`

Now we can see `mega` link is copied.

so let's try to grep mega from the memory dump

`strings ~/my_challenges/evilpepo.vmem | grep mega `

and as a result we will get the mega link let's download the file we can see it is `veracrypt` file just download veracrypt and mount the file and use the same password `abracadabra`

and we got the flag.

### Flag

`Trollcat{y0u_got_n1ce_Skills!}`