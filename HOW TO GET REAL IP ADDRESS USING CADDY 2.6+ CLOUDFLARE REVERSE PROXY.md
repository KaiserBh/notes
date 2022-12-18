you don't.
bye.

Anyway there is many ways but what I found out to be the easiest method is:

we can use the `header_upstream` directive to pass the `CF-Connecting-IP` header to our backend server when using the `reverse_proxy` directive. Here's an example of how we can modify our Caddy configuration file to do this:

```c
sub.domain.com {
  reverse_proxy localhost:4000 {
    header_up CF-Connecting-IP {remote}
  }
}

```

This configuration will pass the real IP of the visitor to our backend server in the `CF-Connecting-IP` header. We can then use this header to access the real IP of the visitor in our backend application. 

It's worth noting that this approach will only work if we are using Cloudflare's flexible/full? maybe strict I am not sure I didn't try it on strict I tried it on full SSL/TLS encryption mode. If we are using the full or strict SSL/TLS modes, the real IP of the visitor will not be preserved, and we will need to use a different approach to access the real IP.

If that doesn't work for you then try this approach instead:
using the `reverse_proxy` directive and the `trusted_proxies` and `header_up` directives is a good way to restore the real IP of a visitor.

The `trusted_proxies` directive is used to specify a list of IP addresses or ranges that are trusted to send the real IP of the visitor in the `CF-Connecting-IP` header. This is necessary because Cloudflare's IP addresses are used to proxy traffic to our backend server, and without the `trusted_proxies` directive, Caddy will not trust the `CF-Connecting-IP` header and will not restore the real IP of the visitor.

The `header_up` directive is used to pass the `CF-Connecting-IP` header to our backend server. This allows us to access the real IP of the visitor in our backend application.

please go to https://www.cloudflare.com/ips/ to get their proxy ips and add them like so:

```c
sub.domain.com {  
  reverse_proxy localhost:4000 {  
    trusted_proxies 173.245.48.0/20 103.21.244.0/22 103.22.200.0/22 103.31.4.0/22 108.162.192.0/18 190.93.240.0/20 141.101.64.0/18 188.114.96.0/20 198.41.128.0/17 197.234.240.0/22 162.158.0.0/15 104.16.0.0/13 104.24.0.0/14 172.64.0.0/13 131.0.72.0/22  
    header_up CF-Connecting-IP {remote}  
  }  
}
```
