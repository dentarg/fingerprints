# fingerprints

## `known_fingerprint()`

Read `~/.ssh/known_hosts` and print the fingerprint for a known host.

```shell
$ known_fingerprint
Usage: hostname
```

```shell
$ known_fingerprint myserver
2048 54:8f:44:26:d8:f0:a9:bf:d1:2f:c0:46:c6:0f:6e:de myserver (RSA)
```

## `fingerprints()`

Print the fingerprints for the current host.

```shell
server$ fingerprints
1024 b5:07:e0:89:7b:8a:03:0a:ec:9d:fb:21:72:1e:58:a1  root@server.example.org (DSA)
2048 4a:67:ff:a7:5e:8b:38:68:1b:d6:9a:a8:de:0e:86:a2  root@server.example.org (RSA)
256 bc:a0:59:4b:2d:b5:1e:75:fe:34:ff:c0:ad:81:c7:00  root@server.example.org (ECDSA)
```

### Run `fingerprints()` on multiple servers

Log in to all servers in a file called `hosts` and print their fingerprints. This command assumes you are using zsh and that your `.zshrc` loads the `fingerprints()` function.

```shell
for host in `cat hosts` ; do ; ssh -t $host "source .zshrc; fingerprints" ; done
```
