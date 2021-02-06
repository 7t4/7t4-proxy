# 7T4 Proxy

Currently this is a build of Nginx on Alpine which includes:

  * [ModSecurity v3](https://github.com/SpiderLabs/ModSecurity) using the [ModSecurity v3 Nginx Connector](https://github.com/SpiderLabs/ModSecurity-nginx) and the [OWASP Core Rule Set](https://github.com/SpiderLabs/owasp-modsecurity-crs)
  * [GeoIP2](https://github.com/leev/ngx_http_geoip2_module) with the [dbip databases](https://db-ip.com/)
  * a few additional general security features
  * [Brotli](https://github.com/google/ngx_brotli)
  * [Certbot](https://certbot.eff.org)

NOTES:
  * The compose file is intended for a swarm deployment. Details on swarm storage to be updated.
  * LetsEncyrpt certbot config/setup is incomplete currently.


The build on the files in the ```conf``` directory.

```conf/modsec``` contains files that link to our owasp rules and contain general modsec settings

```conf/nginx``` contains our nginx, http, and https config files. The default http and https server blocks are built with the expectation of using php. You will need to remove the php block and rules if you are using a different language.

```conf/owasp``` contains our owasp core rule set config

This image was originally based on [andrewnk/docker-alpine-nginx-modsec](https://github.com/andrewnk/docker-alpine-nginx-modsec).
