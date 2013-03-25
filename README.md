# nginx-forward-proxy

Forward proxy configuration for nginx.

Any requests to hostname with suffix ".devel" will be forwarded to localhost.

- http://example.com/foo -> http://example.com/foo
- http://example.com.devel/bar -> http://localhost/bar
- http://example.org.devel:3000/buz -> http://localhost:3000/buz

# Usage

You need to install nginx at first.

```sh
git clone http://github.com/kawanet/nginx-forward-proxy.git
cd nginx-forward-proxy
etc/init.d/nginx-proxy start
tail -f logs/access.log
```

This will launch a HTTP proxy server at port 3128.

## Installing nginx (Mac OS X)

```sh
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
brew install nginx
```

# Author

@kawanet
