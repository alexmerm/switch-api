# switch-api

Simple http server that triggers system commands on predefined URLs

- used in conjunction with https://home-assistant.io/components/switch.rest/
- http://pm2.keymetrics.io for automatic startup

[![Known Vulnerabilities](https://snyk.io/test/github/ycardon/switch-api/badge.svg)](https://snyk.io/test/github/ycardon/switch-api)

## usage

Control macbook display (on macOS Mojave)
- GET /display : get current screen state (sleeping or not)
- POST /display body=ON|OFF : switch screeen state

Get battery power status (on macOS Mojave)
- GET /power : battery power status

## useful commands

- sleep display: `pmset displaysleepnow`
- wake display: `caffeinate -u -t 1`
- test state : `pmset -g powerstate IODisplayWrangler | tail -1 | cut -c29` result <4 are sleeping
- battery power status : `pmset -g batt` (and a painful parsing)
