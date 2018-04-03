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

## Base 64 encode a string

```bash
echo -n 'input' | openssl base64
```
