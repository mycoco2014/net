##socks5 proxy

* add tcp connect timeout
* add tcp read timeout
* add tcp write timeout

```
	dialer,err := proxy.SOCKS5("tcp",tmpProxy.host,nil,proxy.Direct,
		2 * time.Second,
		4 * time.Second,
	)
	if err != nil {
		log.Printf("[ERROR1] %s proxy.SOCKS5 %s\r\n", tmpProxy.host, err )
		return false,0
	}
	// tcp connec timeout
	connDealLine := time.Duration( 3 * time.Second )
	conn, err := dialer.DialTimeout("tcp", CHECK_DOMAIN, connDealLine)
```
