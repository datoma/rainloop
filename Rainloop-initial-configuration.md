To configure rainloop, use admin panel found at : https://webmail.domain.tld/?admin

:bulb: Don't forget to add a new A/CNAME record in your DNS zone.

Default login is "**admin**", password is "**12345**".

You must add and configure your domains in your admin panel like this :

![](http://i.imgur.com/RbMVhkz.png)

### SMTP/IMAP configuration :
![](http://i.imgur.com/GFbbJzs.png)

### SIEVE configuration :
![](http://i.imgur.com/ervKtrG.png)

### Users whitelist :
![](http://i.imgur.com/8Y0ppLb.png)

## Troubleshooting

```bash
# docker logs -f rainloop

nginx: [alert] could not open error log file: open() "/var/lib/nginx/logs/error.log" failed (13: Permission denied)
```

This issue can append with some specific file systems. If that happens, use `nginx` user inside the container :

```yml
rainloop:
  environment:
    - UID=nginx
    - GID=nginx
```