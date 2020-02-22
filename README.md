# docker-vagrant

## 導入手順

```
Vagrantfile + mutagen.yml をdockerのディレクトリに解凍

### vagrant をinstall
https://www.vagrantup.com/downloads.html

### vagrant plugin をinstall
vagrant plugin install vagrant-disksize vagrant-hostsupdater vagrant-mutagen

### mutagen をinstall
brew install mutagen-io/mutagen/mutagen

### 起動
vagrant up

### ssh
vagrant ssh

### docker
docker-compose up

### access example
# http://192.168.51.10:4000
```

# help
### mutagen error

```
Connecting to agent (POSIX)...
Error: unable to create synchronization session (app): create failed: unable to connect to beta: unable to connect to endpoint: unable to dial agent endpoint: agent handshake failed with error output:
vagrant@127.0.0.1: Permission denied (publickey).
==> default: [vagrant-mutagen] Failed to start mutagen project (see error above)
```

~/.ssh/configのvagrantによって追記された箇所を削除

```:example
# VAGRANT: 1591f1f7aa780e1928d9fe48d7899580 (default) / 00bab718-84de-478d-8fd6-7f5e35a92ce3
Host
# VAGRANT: 1591f1f7aa780e1928d9fe48d7899580 (default) / 00bab718-84de-478d-8fd6-7f5e35a92ce3
```

### mutagen delete

mutagenのセッションが生き残っている場合がある

```
mutagen sync list
mutagen sync terminate SESSION_ID
```

### vagrant delete

vagrantを消したい時

```
vagrant halt
vagrant destroy
```
