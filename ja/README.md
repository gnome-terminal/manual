# Project V

![English](resources/englishc.svg) [![Chinese](resources/chinese.svg)](https://www.v2ray.com/) [![German](resources/german.svg)](https://www.v2ray.com/de/) [![Translate](resources/lang.svg)](https://crowdin.com/project/v2ray)

Project V is a set of tools to help you build your own privacy network over internet.

## Introduction

Project V provides a single core with various GUI programs. The core, V2Ray, is for network connection, routing and data processing, while GUI programs are for user friendly experience.

V2Ray's responsibility is transfer data from its client to specified server, based on user configuration. It runs as a commandline tool. It can be configured via JSON based configuration.

## Features

### Multiple proxy support

V2Ray supports Socks, HTTP, Shadowsocks and VMess protocol.

* One V2Ray process can use different protocols on different ports at the same time;
* By combining different inbound and outbound proxies, one can change traffic format dynamically.

### Multiple transport protocols

All proxies above can be send/receive over TLS, TCP, mKCP and more transport protocols.

### Flexible routing

V2Ray has an internal router, which can be configured to proxy traffic, or send directly, or even block them.

## Update this site

This site is generated by GitBook, and host on GitHub. If you'd like to modify its content, please send pull request to [this repo](https://github.com/v2ray/manual).

## License

This website is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).