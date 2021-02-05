# Description

We have caught Mr.EvilPepo and now it is time for you to investigate him we searched his house and we got not much proof we got some report from OSINT department and Our OSINT Investigator told us that he mentioned on his socials "Hack Me if you can, i use same password Everywhere"  we have dumped his computer memory and for further investigation we need your help.
he typed the flag command somewhere and now he forgot it. can you find it?

File: https://mega.nz/file/y90gWRJa#6lJ4qpKw3bfLKvbcTuvcOgGdDpYS9AapC_mwKM-4Zg4

Flag Format: trollcat{}

## Solution

Now we have a memory dump let's run volatility. 

`python2 vol.py -f ~/my_challenges/evilpepo.vmem imageinfo`

```out
INFO    : volatility.debug    : Determining profile based on KDBG search...
          Suggested Profile(s) : Win7SP1x64, Win7SP0x64, Win2008R2SP0x64, Win2008R2SP1x64_24000, Win2008R2SP1x64_23418, Win2008R2SP1x64, Win7SP1x64_24000, Win7SP1x64_23418
                     AS Layer1 : WindowsAMD64PagedMemory (Kernel AS)
                     AS Layer2 : FileAddressSpace (/home/whitewolf/my_challenges/evilpepo.vmem)
                      PAE type : No PAE
                           DTB : 0x187000L
                          KDBG : 0xf80002a3f0a0L
          Number of Processors : 1
     Image Type (Service Pack) : 1
                KPCR for CPU 0 : 0xfffff80002a40d00L
             KUSER_SHARED_DATA : 0xfffff78000000000L
           Image date and time : 2021-01-12 13:22:41 UTC+0000
     Image local date and time : 2021-01-12 18:52:41 +0530
```

we got profile `Win7SP1x64` now the challenge description mentioned about that he typed some command now we have to find it.

`python2 vol.py -f ~/my_challenges/evilpepo.vmem --profile Win7SP1x64 --plugins=volatility-plugins/ consoles`

Now after that we can able to see the flag just add each char and submit it.

### Flag

`trollcat{comands_4r3_important}
`
