# Shell / Linux commands

## Copy folder

```bash
cp -R source destination/
```


## Copy file over SSH

```bash
scp file.txt username@to_host:/remote/directory/
```

`host` can also be an IP address.

## Disk usage of a folder or a file

```bash
du -sh file_path
```

`-s` for summarize, `-h` for human-readable. From [Stackoverflow](https://unix.stackexchange.com/questions/185764/how-do-i-get-the-size-of-a-directory-on-the-command-line). If you want only the top level directories, add the `-d1` flag.


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

## Do an operation on many files


```bash
find . -type f -name "*.tif" -exec sh -c 'convert "${0}" "${0%.tif}.png"' {} \;
```

## Last restart
```bash
who -b
```
Source [here](https://www.cyberciti.biz/tips/linux-last-reboot-time-and-date-find-out.html).


## Do something to a list of files

For example `echo` each file name:

```bash
ls -1 | xargs -L1 echo
```

`L1` means use one line for each argument.

## Run a shell script as another user

```bash
sudo -H -u otheruser bash -c 'echo "I am $USER, with uid $UID"'
```

Fra [stackoverflow](https://askubuntu.com/questions/294736/run-a-shell-script-as-another-user-that-has-no-password).
