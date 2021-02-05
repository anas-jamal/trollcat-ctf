# Description

Now After some good beating, Mr.EvilPepo saying he hides something on the internet. find it

Note: Use the file provided in Mr.EvilPepo Part-1

## Solution

So we according to description we have to search his browser history

`python2 vol.py --plugins=volatility-plugins/ -f ~/my_challenges/evilpepo.vmem --profile Win7SP1x64 chromehistory`

Now we will lots of history there's one link important `https://defuse.ca/b/sOOqp4UunTdD0oUjidJFlz`

but sadly it ask for password now if you have read the desciption of first challenge that Mr.Troll uses same password everywhere now let's dump his computer password.

`python2 vol.py --plugins=volatility-plugins/ -f ~/my_challenges/evilpepo.vmem --profile Win7SP1x64 hashdump`

```out
Administrator:500:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
WhiteWolf:1000:aad3b435b51404eeaad3b435b51404ee:2e6a7cf5aabb33a044684dd9c97e88a7:::
```

now just crack it using [CrackStation](https://crackstation.net/)

`aad3b435b51404eeaad3b435b51404ee : abracadabra`

Now just enter the password on that paste site.


### Flag

`Trollcat{secret_hidden_0nn_th3_1ntern3t}`