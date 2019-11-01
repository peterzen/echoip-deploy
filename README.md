# echoip-deploy

Helper files to run the [echoip](https://github.com/mpolden/echoip) service on an own server, which is connected to multiple networks (public and private).

### `systemd` service
```bash
cp echoip.service /etc/systemd/system/
systemctl enable echoip
systemctl restart echoip
```

### `nginx` configuration file

```bash
cp proxy.conf /etc/nginx
cp default /etc/nginx/sites-available
systemctl nginx restart
```
