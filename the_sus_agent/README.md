# Description

```desc
One of our agent is doing something suspicious on the network can you find out?
```

## Solution 

open the `.pcapng` file in `wireshark` now first of all check `export objects > http` and we can lots of junk but there's one file `welcome.jpg` and now analyze the `HTTP` packets we can see there's a file `secret.jpg` now `follow http stream` and we can see base64 string `aWhvcGV5b3VkaWRub3R0cmllZHRvYnJ1dGVmb3JjZWl0` now after decoding we will get  `ihopeyoudidnottriedtobruteforceit` and finally we have `.jpg` file and a password so just run `steghide` and we will get the flag.

### Flag

`Trollcat{this_challenge_was_easy_right???}
`