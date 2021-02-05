# Description

```desc
Agent Troll recieved some file but not able to read the data can you help us?

Challenge is attached
```

## Solution

In this challenge the header of the file is edited bascially mozilla has it's own archive files `.mar` file.

First of all open the `.car` file in [hexed.it](https://hexed.it/) and we just have to replace `C` to `M` in the hex editor and export it and extract it using mar tool which can be installed by using pip.

visit this link [MAR](https://wiki.mozilla.org/Software_Update:MAR) this is a full guide about `.mar` files.

after installing `mar` run

`mar -x trollcat_fixed.mar`

### Flag

`Trollcat{M0zilla_Archive_maaaarls}`
