This is a collection of scripts I have written or found that simplify some things for me. To use these, I simply check out this
repository into `~/.bin/`, and add that directory to my path in `~/.bash_profile`.

ssh-proxy
---------
`ssh-proxy` allows me to SSH to some host via another SSH proxy host.

Ideally, the proxy host is configured in `~/.ssh/config` and is aliased to something short. As an example:

```
Host my-proxy
    HostName my-proxy.foo.com
    ForwardAgent yes
    ForwardX11Trusted yes
    ProxyCommand none
    User my_user
    ControlMaster auto
    ControlPath ~/.ssh/master-%r@%h:%p
    TCPKeepAlive yes
    ServerAliveInterval 300
```

Using this script, I can proxy to another host with the command:

```
ssh-proxy my-proxy user@remote.bar.com
```
