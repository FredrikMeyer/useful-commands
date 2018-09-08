# Shell commands

## Copy folder

```bash
cp -R source destination/
```


## Copy file over SSH

```bash
scp file.txt username@to_host:/remote/directory/
```

`host` can also be an IP address.

## Less

Used for reading files in the terminal. E.g. `less Main.elm`.

  * Forward search `/`. Backward search with `?`. Next match: `n`, previous match `N`. 
  * Navigation:
    * `ctrl+f` forward one window
    * `ctrl+b` back one window
    * `ctrl+d` forward half a window
    * `ctrl+u`
    * `j` and `k` forward/back a line at a time.
    * `G` end of file. `g` beginning of file.

From [here](https://www.thegeekstuff.com/2010/02/unix-less-command-10-tips-for-effective-navigation/).

## Base 64 encode a string

```bash
echo -n 'input' | openssl base64
```
