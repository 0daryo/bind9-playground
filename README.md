## Bind Playground 
This is playground for dns with docker.
## How to use
### Need
- docker
### Steps
1. build container
```
 % docker build -t bind .
```
2. run container
```
% docker run -d -p 53:53/udp -v $(pwd)/conf:/etc/bind --restart always --name bind bind
```
3. Forward Query
```
 % dig @localhost www.ody.local.

; <<>> DiG 9.10.6 <<>> @localhost www.ody.local.
; (2 servers found)
;; global options: +cmd
;; Got answer:
(...)

;; ANSWER SECTION:
www.ody.local.          3600    IN      A       192.168.0.250

;; Query time: 2 msec
;; SERVER: ::1#53(::1)
;; WHEN: Thu Jun 30 00:18:35 JST 2022
;; MSG SIZE  rcvd: 58
```

