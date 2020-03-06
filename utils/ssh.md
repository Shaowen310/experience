# SSH

## Create SSH Keys

```text
ssh-keygen -t ed25519
```

## SOCKS proxy

```text
ssh -D 1337 -q -C -N user@host
```

1. `-D 1337`: open a SOCS proxy on local port `:1337`.
2. `-C`: compress data in the tunnel, save bandwidth
3. `-q`: quite mode, don't output anything locally
4. `-N`: do not execute remote commands

## OpenSSH on Windows

### WSL

```text
sudo service ssh --full-restart
```

## References

1. [socks proxy linux ssh bypass content filters](https://ma.ttias.be/socks-proxy-linux-ssh-bypass-content-filters/)

