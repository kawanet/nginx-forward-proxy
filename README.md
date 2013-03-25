# nginx-forward-proxy

Forward proxy configuration for nginx.

## Usage

```sh
git clone http://github.com/kawanet/nginx-forward-proxy.git
cd nginx-forward-proxy
etc/init.d/nginx-proxy start
tail -f logs/access.log
```

This will launch a HTTP proxy server at port 3128 per default.

## Local Development

Any requests to hostname with suffix ".devel" will be forwarded to localhost.

- http://example.com/foo -> http://example.com/foo
- http://example.com.devel/bar -> http://localhost/bar
- http://example.org.devel:3000/buz -> http://localhost:3000/buz

Edit `etc/nginx.conf` to specify proxy server's port number, local HTTP server's IP address and port number.

```
  server {
    # proxy server port
    listen 3128;

    location / {
      # local http server host and port
      set $devel_host "127.0.0.1";
      set $devel_port "80";
```

## Installing nginx (Mac OS X)

You need to install nginx before running nginx-forward-proxy.

```sh
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
brew install nginx
```

## Author

@kawanet
