# Træfik <!-- .element: style="margin-left:-5px"-->
### The could Native Edge Router <!-- .element: style="margin-left:-5px"-->

![Traefik](./slides/images/traefik.logo.horizontal.bright.svg) <!-- .element: style="border:none;margin-bottom:-10px" -->

BBL MiPih - Toulouse - 2018/07/02

<small>[Nicolas Mengin](http://twitter.com/nicomengin) - [Containous](http://twitter.com/containous)</small>

Note:
---

## docker inspect me <!-- .element: style="margin-bottom:100px"-->

* Developer for 12 years <!-- .element: class="fragment" data-fragment-index="1" -->
* Part time DevOps <!-- .element: class="fragment" data-fragment-index="1" -->
* ❤ Java (GWT), GO, Shell, Containers World ❤ <!-- .element: class="fragment" data-fragment-index="1" -->
* Work @ Containous <!-- .element: class="fragment" data-fragment-index="2" -->
* Maintainer of <!-- .element: class="fragment" data-fragment-index="2" --> [Træfik](https://traefik.io) <!-- .element: class="fragment" data-fragment-index="2" -->

---

## Træfik explained to my mother

<div class="fragment">
```
Mum : "What are you doing in your new company?"
Me : "I am computing a Reverse Proxy."
Mum : "..."
Me : "Your Internet Box is like a proxy!"
```
</div>
<div class="fragment">
```
Me : "Træfik allows doing the reverse."
```
</div>
<div class="fragment">
```
Mum : "OK! It's like Istio?!"
```
</div>
<div class="fragment">
```
Me : "No, Istio is used for the east-west connections
      Træfik has to be used for the north-south connections"
```
</div>
<div class="fragment">
```
Mum : "OK! It's like Nginx?!"
```
</div>
<div class="fragment">
```
Me : "No, Nginx is a webserver."
```
</div>
<div class="fragment" >
```
Mum : "Understood! It's like HA Proxy!"
```
</div>
<div style="display: none;">
```
```
</div>
![But](./slides/images/greatBut.gif) <!-- .element style="display:none; border:none"-->

Note:

---

## Why another Reverse Proxy?

![Why](./slides/images/why.gif) <!-- .element: style="height:500px;width:600px;"-->

Note:

-

## A long time ago in a galaxy far, far away.... <!-- .element: style="margin-left:-50px"-->

1. Deploy a service to expose <!-- .element: style="margin-top: 100px; margin-left:-400px" class="fragment" data-fragment-index="1" -->
1. Configure the Reverse Proxy <!-- .element: style="margin-left:-400px" class="fragment" data-fragment-index="2" -->
1. Reload/Restart it. <!-- .element: style="margin-left:-400px" class="fragment" data-fragment-index="3" -->

<p style="margin-top:200px;font-size: 200%;color:white" class="fragment">**In a static way!!**</p>

![Old archi](./slides/images/old-archi.png) <!-- .element: style="float: right; width: 60%; margin-right:-200px; margin-top:-500px"-->

Note:

-

## Static infrastructure is (almost) dead!

![New archi](./slides/images/newarchi-RP.png) <!-- .element: style="background-color:white; height:480px; margin-top:-20px; margin-bottom: -35px" class="fragment fade-out" data-fragment-index="1" -->
![New archi02](./slides/images/newarchi-RP-config.png) <!-- .element: style="background-color:white; height:480px; margin-top:-500px;" class="fragment" data-fragment-index="1" -->

<p style="margin-top:-40px;font-size: 125%;color:white" class="fragment">**How to configure dynamic infrastructures?**</p>

Note:

---

## One Reverse Proxy to rule them all

![Traefik](./slides/images/traefik.logo.bright.svg)

-

### Dynamic configuration for dynamic infrastruture

![New archi](./slides/images/newarchi-Traefik.png) <!-- .element: style="background-color:white;"-->

Note:

-

## Træfik in details

* Reverse Proxy Dynamic <!-- .element: style=" margin-left:-300px"-->
* Written in GO (Single binary) <!-- .element: style="margin-left:-300px"-->
* Open Source <!-- .element: style="margin-left:-300px"-->
* Docker official image <!-- .element: style="margin-left:-300px"-->
* Multi-Backends <!-- .element: style="margin-left:-300px"-->
* Hot reloading <!-- .element: style="margin-left:-300px"-->
* Load-balancing: WRR, DRR <!-- .element: style="margin-left:-300px"-->
* Circuit breakers <!-- .element: style="margin-left:-300px"-->
* ACME <!-- .element: style="margin-left:-300px"-->
* Websockets <!-- .element: style="margin-left:-300px"-->
* HTTP2 <!-- .element: style="margin-left:-300px"-->
* ... <!-- .element: style="margin-left:-300px"-->

![Features](./slides/images/wordcloud.png) <!-- .element: style="border:none; float: right; width: 50%; margin-top: -525px; margin-right:-150px"-->

Note:

-

## Træfik versions

* Træfik camembert (2016/11) <!-- .element: style=" margin-left:-400px"-->
  * Cluster mode
  * Swarm Mode
  * Generic Mesos
  * Basic Authentication (Global)
  * Session Affinity
* Træfik morbier (2017/03) <!-- .element: style=" margin-top:20px; margin-left:-400px"-->
  * **Rancher (API)**
  * Eureka
  * Prometheus
  * Healthcheks
  * Traefik bug

![Features](./slides/images/traefik-morbier.png) <!-- .element: style="float: right; width: 25%; margin-top: -620px; margin-right:-150px"-->

Note:

-

## Træfik versions

* Træfik raclette (2017/05)<!-- .element: style=" margin-left:-400px"-->
  * **Rancher (MetaData)**
  * Basic Authentication (Frontend)
  * DynamoDB
  * DashBoard Filter
* Træfik roquefort (2017/10) <!-- .element: style=" margin-top:20px; margin-left:-400px"-->
  * GRPC
  * Auth Forward
  * Custom Error Pages
  * DataDog & StatD
  * Proxy Protocol
  * Images Multi Arch...

![Features](./slides/images/traefik-raclette.svg) <!-- .element: style=" float: right; width: 23%;  margin-top: -600px; margin-right:-125px"-->
![Features](./slides/images/traefik-roquefort.svg) <!-- .element: style=" float: right; width: 30%;  margin-top: -250px; margin-right:-150px"-->
-

## Træfik versions

* Træfik cancoillotte (2018/01) <!-- .element: style=" margin-left:-400px"-->
  * Rate Limiting
  * ETCD V3
  * Dynamic TLS certificates
  * Custom Headers
  * Service Fabric
  * ACME HTTP-01 challenge
* Træfik Tête de Moine (2018/05)<!-- .element: style=" margin-left:-400px"-->
  * Let's Encrypt wildcards
  * Open Tracing
  * K8s secrets
  * Access log filtering

![Features](./slides/images/traefik-cancoillotte.svg) <!-- .element: style="float: right; width: 40%;  margin-top: -575px; margin-right:-100px"-->
![Features](./slides/images/traefik-tete-de-moine.svg) <!-- .element: style="float: right; width: 50%;  margin-top: -250px; margin-right:-150px"-->
---

<!-- .slide: data-background="./slides/images/pray-cat.jpeg" -->

# DEMO  <!-- .element: style="float: right; width: 50%; margin-right:-200px; color: white"-->

Note:

---

## Let's focus on...

* Rancher Integration
* Security
* Metrics and Tracing

---
## What about Rancher?

* Support from Træfik V1.2
* API and MetaData
* One contributor from Rancher
* Rancher V2.0 => WIP
* 2 ways to use Træfik
  * Træfik image in Rancher Catalog
  * Thanks to docker-compose service

-

## Let's talk about Security...

* Auto-generated unsigned certificate <!-- .element: style="margin-top: 40px; margin-left: -150px" class="fragment" data-fragment-index="1" -->
* Statically provided certificates <!-- .element: style="margin-left: -150px" class="fragment" data-fragment-index="2" -->
* Dynamically provided certificates <!-- .element: style="margin-left: -150px"  class="fragment" data-fragment-index="3" -->
  * File and KV store <!-- .element:  class="fragment" data-fragment-index="3" -->
* Let's Encrypt certificates <!-- .element: style="margin-left: -150px"  class="fragment" data-fragment-index="4" -->
  * Challenges DNS and HTTP <!-- .element: class="fragment" data-fragment-index="5" -->
  * Dynamic <!-- .element: class="fragment" data-fragment-index="5" -->
  * Renewed automatically <!-- .element: class="fragment" data-fragment-index="5" -->
  * Stored in file or KV store <!-- .element: class="fragment" data-fragment-index="5" -->
  * Wildcards <!-- .element: class="fragment" data-fragment-index="5" -->

<div style="float: right; width: 40%; margin-top: -450px; margin-right: -200px" data-fragment-index="1" class="fragment">
<div data-fragment-index="2" class="fragment fade-out" >
```toml
[entryPoints]
  [entryPoints.https]
  address = ":443"
    [entryPoints.https.tls]
```
</div>
</div>
<div style="float: right; width: 62%; margin-top: -400px; margin-right: -300px" data-fragment-index="2" class="fragment">
<div data-fragment-index="3" class="fragment fade-out" >
```toml
[entryPoints]
  [entryPoints.https]
  address = ":443"
    [entryPoints.https.tls]
      [[entryPoints.https.tls.certificates]]
       CertFile = "/snitest.com.cert"
       KeyFile = "/snitest.com.key"
```
</div>
</div>
<div style="float: right;  width: 50%; margin-top: -350px; margin-right: -200px" data-fragment-index="3" class="fragment">
<div data-fragment-index="4" class="fragment fade-out" >
```toml
[entryPoints]
  [entryPoints.https]
  address = ":443"
    [entryPoints.https.tls]

[file]

[[tlsConfiguration]]
entryPoints = ["https"]
  [tlsConfiguration.certificate]
     CertFile = "/snitest.com.cert"
     KeyFile = "/snitest.com.key"
```
</div>
</div>
<div style="float: right; width: 40%; margin-top: -250px; margin-right: -200px" data-fragment-index="5" class="fragment">
```toml
[entryPoints]
  [entryPoints.http]
  address = ":80"
  [entryPoints.https]
  address = ":443"
    [entryPoints.https.tls]

[acme]
email = "test@traefik.io"
storage = "/acme.json"
entryPoint = "https"
OnHostRule = true
  [acme.httpChallenge]
  entryPoint = "http"
```
</div>
![LE](./slides/images/letsencrypt-logo.svg) <!-- .element: style="display:none" class="fragment" data-fragment-index="4" -->

Note:

-

## Metrics and Tracing

* Metrics <!-- .element: style="margin-top: 40px" class="fragment" data-fragment-index="1" -->
  * Prometheus (+ Grafana) <!-- .element: class="fragment" data-fragment-index="1" -->
  * DataDog, StatD <!-- .element: class="fragment" data-fragment-index="1" -->
  * Predefined data (requests, backends)  <!-- .element: class="fragment" data-fragment-index="1" -->
  * Official Grafana configuration  <!-- .element: class="fragment" data-fragment-index="1" -->
* Open Tracing <!-- .element: style="margin-top: 20px;" class="fragment" data-fragment-index="2" -->
  * Jaeger, ZipKin <!-- .element: class="fragment" data-fragment-index="2" -->
  * Predefined spans (retry, authentication...) <!-- .element: class="fragment" data-fragment-index="2" -->

Note:

---

<!-- .slide: data-background="./slides/images/pray02.jpg" data-background-size="1500px" -->

# DEMO  <!-- .element: style="margin-top:200px; color: white"-->

---

## Few key figures <!-- .element: style="margin-bottom:50px"-->

Version 1.6.4</BR>
+16000 &#9734;</BR>
+100M Downloads</BR>
+/-1600 LGTM</BR>
+220 Contributors

![Features](./slides/images/100m.png) <!-- .element: style="border:none; float: center; width: 40%; margin-top:30px"-->

Note:

-

## Containous <!-- .element: style="margin-top: 0px; margin-bottom: 50px"-->

Since 2016</BR>
Raised 1M€</BR>
10 developers</BR>
Commercial support</BR>
More information on [containo.us](https://containo.us/)

-

# STICKERS

![Traefik](./slides/images/traefik.logo.bright.svg) <!-- .element: style="border:none" -->

---

# THANK YOU <!-- .element: style="margin-bottom: 100px;"-->

[containo.us](https://containo.us/)
</BR>
[traefik.io](http://traefik.io)
</BR>
[@traefikproxy](http://twitter.com/traefikproxy)
</BR>
[@nicomengin](http://twitter.com/nicomengin)
</BR>
[nmengin.github.io/bbl-mipih/](https://nmengin.github.io/bbl-mipih/)
