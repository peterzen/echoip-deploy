# echoip-deploy

Helper files to run the [echoip](https://github.com/mpolden/echoip) service on an own server, which is connected to multiple networks (public and private).

### Installation
* Install `echoip` binary to `/usr/local/bin`
* Create `echoip user`: `adduser echoip`
* `cp index.html /home/echoip`

### GeoIP database

* Install [GeoIP update](https://github.com/maxmind/geoipupdate/releases)
* `cp GeoIP.conf /etc`
* `su - echoip`
* Run `geoipupdate -d /home/echoip`
* Install `crontab` entry: 
```
15 1 * * 5 /usr/local/bin/geoipupdate -d /home/echoip
```

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
