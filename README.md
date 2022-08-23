# Matomo @ DHL

This is a quick and easy way to get a local Matomo instance running on your own development environment.

## Requirements

- [Docker](https://www.docker.com/)

## Startup:

```shell
docker-compose up
```
... and point your browser to [http://localhost:8888/](http://localhost:8888/).

## Installation

When Matomo is opened [in the browser](http://localhost:8888/), you need to configure the application. Very important 
in the database configuration step is to use `db` as the hostname and **not** `localhost` or `127.0.0.1`.

## Configuration

On the `JavaScript Tracking Code` page, you will receive a html snippet that looks a little but like this:

```html
<!-- Matomo -->
<script>
  var _paq = window._paq = window._paq || [];
  /* tracker methods like "setCustomDimension" should be called before "trackPageView" */
  _paq.push(['trackPageView']);
  _paq.push(['enableLinkTracking']);
  (function() {
    var u="//172.18.0.3/";
    _paq.push(['setTrackerUrl', u+'matomo.php']);
    _paq.push(['setSiteId', '1']);
    var d=document, g=d.createElement('script'), s=d.getElementsByTagName('script')[0];
    g.async=true; g.src=u+'matomo.js'; s.parentNode.insertBefore(g,s);
  })();
</script>
<!-- End Matomo Code -->
```
... where, of course, the `setSiteId` can change but is normally **1** for initial setups.

