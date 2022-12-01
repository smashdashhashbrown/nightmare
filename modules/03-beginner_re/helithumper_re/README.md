# Writeup

Pop the binary into GHIDRA and load up the `main` function. An function of interest here will be the
`validate` function, which takes our user input.

Inside the `validate` function, we see the following:
```
  local_10 = *(long *)(in_FS_OFFSET + 0x28);
  local_48[0] = 0x66;
  local_48[1] = 0x6c;
  local_48[2] = 0x61;
  local_48[3] = 0x67;
  local_38 = 0x7b;
  local_34 = 0x48;
  local_30 = 0x75;
  local_2c = 0x43;
  local_28 = 0x66;
  local_24 = 0x5f;
  local_20 = 0x6c;
  local_1c = 0x41;
  local_18 = 0x62;
  local_14 = 0x7d;
```

The function locally declares a string byte-by-byte which resolves to: `flag{HuCf_lAb}`. The for loop following
the string declaration is a for loop looping through both our string and the password string byte by byte doing an `==`
condition.

