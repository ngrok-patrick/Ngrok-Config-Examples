# Ngrok Config Examples

This simply contains Many Examples of Ngrok Config (ngrok.yml) Files.

Hopefully, if someone is looking for a particular configuration, this
might pop up on Google, and help someone.

### Two Tunnels, One Agent
<sup>You get 2 Tunnels with Free Ngrok Service</sup>
```
version: "2"
authtoken: noTokenProvided
console_ui_color: transparent
api_key: noTakeyMyKeyee

tunnels:
    tun1:
        proto: http
        addr: localhost:80
        subdomain: spearmint178
    tun2:
        proto: http
        addr: http://youngfunastoundingsecret.neverssl.com
```

### Mother of All Ngrok.yml's ([https://ngrok.com/docs/ngrok-agent/config](https://ngrok.com/docs/ngrok-agent/config))

```
version: "2"
authtoken: squashToken
api_key: NoTakeyMyKeyee
connect_timeout: 30s
console_ui: true
console_ui_color: transparent
dns_resolver_ips:
  - 1.1.1.1
  - 8.8.8.8
heartbeat_interval: 1m
heartbeat_tolerance: 5s
inspect_db_size: 104857600 # 100mb
inspect_db_size: 50000000
log_level: info
log_format: json
log: /var/log/ngrok.log
metadata: '{"serial": "00012xa-33rUtz9", "comment": "For customer alan@example.com"}'
proxy_url: socks5://localhost:9150
region: us
remote_management: false
root_cas: trusted
update_channel: stable
update_check: false
version: 2
web_addr: localhost:4040

tunnels:

  website:
    addr: 8888
    basic_auth:
      - "bob:bobpassword"
    schemes:
      - https
    host_header: "myapp.dev"
    inspect: false
    proto: http
    subdomain: myapp

  e2etls:
    addr: 9000
    proto: tls
    hostname: myapp.example.com
    crt: example.crt
    key: example.key

  ssh-access:
    addr: 22
    proto: tcp
    remote_addr: 1.tcp.ngrok.io:12345

  my-cool-website:
    labels:
      - region=us-east
      - team=infra
    addr: 8000
    inspect: false
```

