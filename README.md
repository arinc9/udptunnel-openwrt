Add udptunnel feed to the bottom of `feeds.conf.default`:
```
src-git udptunnel https://github.com/arinc9/udptunnel-openwrt.git
```

Refresh feeds and install v2ray feed
```
./scripts/feeds update -a && ./scripts/feeds install -a
```
