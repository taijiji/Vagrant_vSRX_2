# Vagrant Juniper vSRX

# Build

```
$ vagrant init

...


$ vagrant status

Current machine states:

vsrx1                     running (virtualbox)

```

# Access and Login

```
$ vagrant ssh vsrx1

--- JUNOS 12.1X47-D15.4 built 2014-11-12 02:13:59 UTC

root@vsrx%

root@vsrx% cli

root@vsrx>

root@vsrx> show version
Hostname: vsrx
Model: firefly-perimeter
JUNOS Software Release [12.1X47-D15.4]
```

# add configuration for general use

## vSRX

```
edit

set system root-authentication plain-text-password
set system login user user1 class super-user
set system login user user1 authentication plain-text-password

set security zones security-zone trust interfaces ge-0/0/1
set security zones security-zone trust interfaces ge-0/0/1.0 host-inbound-traffic system-services all
set system time-zone Asia/Tokyo

set system services netconf ssh

delete security policies
set security forwarding-options family mpls mode packet-based
set security forwarding-options family inet6 mode packet-based
```

# Reference
## Japanese article
- [Vagrantでfireflyを動かしたら自動化開発が捗った話](https://qiita.com/taijijiji/items/501a4d671106240fbd2c)
