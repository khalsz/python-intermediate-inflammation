Last login: Wed Oct  2 09:32:51 on ttys112
ds2718@N0897-MAC ~ % ssh localadmin@lakefs.apps.l
ssh: Could not resolve hostname lakefs.apps.l: nodename nor servname provided, or not known
ds2718@N0897-MAC ~ % ssh
usage: ssh [-46AaCfGgKkMNnqsTtVvXxYy] [-B bind_interface] [-b bind_address]
           [-c cipher_spec] [-D [bind_address:]port] [-E log_file]
           [-e escape_char] [-F configfile] [-I pkcs11] [-i identity_file]
           [-J destination] [-L address] [-l login_name] [-m mac_spec]
           [-O ctl_cmd] [-o option] [-P tag] [-p port] [-R address]
           [-S ctl_path] [-W host:port] [-w local_tun[:remote_tun]]
           destination [command [argument ...]]
       ssh [-Q query_option]
ds2718@N0897-MAC ~ % ssh localadmin@lakefs.apps.l
ssh: Could not resolve hostname lakefs.apps.l: nodename nor servname provided, or not known
ds2718@N0897-MAC ~ % cd .ssh
ds2718@N0897-MAC .ssh % ls
config		id_ed25519	id_ed25519.pub	known_hosts
ds2718@N0897-MAC .ssh % vim config
ds2718@N0897-MAC .ssh % vpn
Password:
VPN account password: 
INFO:   Connected to gateway.
Please enter one-time password: 
INFO:   Authenticated.
INFO:   Remote gateway has allocated a VPN.
Thu Oct  3 10:23:51 2024 : publish_entry SCDSet() failed: Success!
Thu Oct  3 10:23:51 2024 : publish_entry SCDSet() failed: Success!
Thu Oct  3 10:23:51 2024 : Using interface ppp0
Thu Oct  3 10:23:51 2024 : Connect: ppp0 <--> /dev/ttys113
INFO:   Got addresses: [10.215.129.217], ns [10.111.4.65, 10.111.4.66], ns_suffix [jet.uk;ccfe.ac.uk;ukaea.uk;jet.efda.org]
INFO:   Negotiation complete.
Thu Oct  3 10:23:51 2024 : local  IP address 10.215.129.217
Thu Oct  3 10:23:51 2024 : remote IP address 169.254.2.1
Thu Oct  3 10:23:51 2024 : primary   DNS address 10.111.4.65
Thu Oct  3 10:23:51 2024 : secondary DNS address 10.111.4.66
Thu Oct  3 10:23:51 2024 : Committed PPP store
Thu Oct  3 10:23:51 2024 : Committed PPP store
INFO:   Interface ppp0 is UP.
INFO:   Setting new routes...
add host 194.81.223.65: gateway 10.22.8.1
delete net 0.0.0.0: gateway 10.22.8.1
add net 0.0.0.0: gateway ppp0
INFO:   Tunnel is up and running.
INFO:   Cancelling threads...
INFO:   Cleanup, joining threads...
INFO:   Setting ppp0 interface down.
INFO:   Restoring routes...
delete host 194.81.223.65: gateway 10.22.8.1
delete net 0.0.0.0: gateway ppp0
add net 0.0.0.0: gateway 10.22.8.1
Thu Oct  3 12:03:04 2024 : Hangup (SIGHUP)
Thu Oct  3 12:03:04 2024 : Modem hangup
Thu Oct  3 12:03:04 2024 : Connection terminated.
Thu Oct  3 12:03:04 2024 : LCP close (User request).
Thu Oct  3 12:03:04 2024 : Connect time 99.3 minutes.
Thu Oct  3 12:03:04 2024 : Sent 27609968 bytes, received 130730398 bytes.
ERROR:  pppd: The link was terminated by the modem hanging up.
INFO:   Terminated pppd.
INFO:   Closed connection to gateway.
INFO:   Logged out.
ds2718@N0897-MAC .ssh % curl ifconfig.me
194.81.223.66%                                                                                                                                                                                                      ds2718@N0897-MAC .ssh % ping 80.192.216.30
PING 80.192.216.30 (80.192.216.30): 56 data bytes
64 bytes from 80.192.216.30: icmp_seq=0 ttl=51 time=53.912 ms
64 bytes from 80.192.216.30: icmp_seq=1 ttl=51 time=50.860 ms
64 bytes from 80.192.216.30: icmp_seq=2 ttl=51 time=45.815 ms
64 bytes from 80.192.216.30: icmp_seq=3 ttl=51 time=49.754 ms
^C
--- 80.192.216.30 ping statistics ---
5 packets transmitted, 4 packets received, 20.0% packet loss
round-trip min/avg/max/stddev = 45.815/50.085/53.912/2.898 ms
ds2718@N0897-MAC .ssh % curl ifconfig.me  
194.81.223.66%                                                                                                                                                                                                      ds2718@N0897-MAC .ssh % cd 
ds2718@N0897-MAC ~ % brew install ngrok 
==> Auto-updating Homebrew...
Adjust how often this is run with HOMEBREW_AUTO_UPDATE_SECS or disable with
HOMEBREW_NO_AUTO_UPDATE. Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Auto-updated Homebrew!
Updated 3 taps (homebrew/services, homebrew/core and homebrew/cask).
==> New Casks
furtherance

You have 15 outdated formulae installed.

==> Caveats
To install shell completions, add this to your profile:
  if command -v ngrok &>/dev/null; then
    eval "$(ngrok completion)"
  fi

==> Downloading https://raw.githubusercontent.com/Homebrew/homebrew-cask/ba16a007e7c7ab5a69a112a668557ca17d84e72b/Casks/n/ngrok.rb
############################################################################################################################################################################################################# 100.0%
==> Downloading https://bin.equinox.io/a/dW4eR4uyHNy/ngrok-v3-3.16.1-stable-darwin-arm64.zip
############################################################################################################################################################################################################# 100.0%
==> Installing Cask ngrok
==> Linking Binary 'ngrok' to '/opt/homebrew/bin/ngrok'
🍺  ngrok was successfully installed!
ds2718@N0897-MAC ~ % redis-cli ping
PONG
ds2718@N0897-MAC ~ % ngrok http 6379
http - start an HTTP tunnel

USAGE:
  ngrok http [address:port | port] [flags]

AUTHOR:
  ngrok - <support@ngrok.com>

COMMANDS: 
  config          update or migrate ngrok's configuration file
  http            start an HTTP tunnel
  tcp             start a TCP tunnel
  tunnel          start a tunnel for use with a tunnel-group backend

EXAMPLES: 
  ngrok http 80                                                 # secure public URL for port 80 web server
  ngrok http --url baz.ngrok.dev 8080                           # port 8080 available at baz.ngrok.dev
  ngrok tcp 22                                                  # tunnel arbitrary TCP traffic to port 22
  ngrok http 80 --oauth=google --oauth-allow-email=foo@foo.com  # secure your app with oauth

Paid Features: 
  ngrok http 80 --url mydomain.com                              # run ngrok with your own custom domain
  ngrok http 80 --cidr-allow 2600:8c00::a03c:91ee:fe69:9695/32  # run ngrok with IP policy restrictions
  Upgrade your account at https://dashboard.ngrok.com/billing/subscription to access paid features

Upgrade your account at https://dashboard.ngrok.com/billing/subscription to access paid features

Flags:
  -h, --help      help for ngrok

Use "ngrok [command] --help" for more information about a command.

ERROR:  authentication failed: Usage of ngrok requires a verified account and authtoken.
ERROR:  
ERROR:  Sign up for an account: https://dashboard.ngrok.com/signup
ERROR:  Install your authtoken: https://dashboard.ngrok.com/get-started/your-authtoken
ERROR:  
ERROR:  ERR_NGROK_4018
ERROR:  https://ngrok.com/docs/errors/err_ngrok_4018
ERROR:  
ds2718@N0897-MAC ~ % ngrok tcp  6379
tcp - start a TCP tunnel

USAGE:
  ngrok tcp [address:port | port] [flags]

AUTHOR:
  ngrok - <support@ngrok.com>

COMMANDS: 
  config          update or migrate ngrok's configuration file
  http            start an HTTP tunnel
  tcp             start a TCP tunnel
  tunnel          start a tunnel for use with a tunnel-group backend

EXAMPLES: 
  ngrok http 80                                                 # secure public URL for port 80 web server
  ngrok http --url baz.ngrok.dev 8080                           # port 8080 available at baz.ngrok.dev
  ngrok tcp 22                                                  # tunnel arbitrary TCP traffic to port 22
  ngrok http 80 --oauth=google --oauth-allow-email=foo@foo.com  # secure your app with oauth

Paid Features: 
  ngrok http 80 --url mydomain.com                              # run ngrok with your own custom domain
  ngrok http 80 --cidr-allow 2600:8c00::a03c:91ee:fe69:9695/32  # run ngrok with IP policy restrictions
  Upgrade your account at https://dashboard.ngrok.com/billing/subscription to access paid features

Upgrade your account at https://dashboard.ngrok.com/billing/subscription to access paid features

Flags:
  -h, --help      help for ngrok

Use "ngrok [command] --help" for more information about a command.

ERROR:  authentication failed: Usage of ngrok requires a verified account and authtoken.
ERROR:  
ERROR:  Sign up for an account: https://dashboard.ngrok.com/signup
ERROR:  Install your authtoken: https://dashboard.ngrok.com/get-started/your-authtoken
ERROR:  
ERROR:  ERR_NGROK_4018
ERROR:  https://ngrok.com/docs/errors/err_ngrok_4018
ERROR:  
ds2718@N0897-MAC ~ % python3 -m http.server 6379
Serving HTTP on :: port 6379 (http://[::]:6379/) ...
^C
Keyboard interrupt received, exiting.
ds2718@N0897-MAC ~ % ping 80.192.216.30
PING 80.192.216.30 (80.192.216.30): 56 data bytes
64 bytes from 80.192.216.30: icmp_seq=0 ttl=51 time=48.485 ms
64 bytes from 80.192.216.30: icmp_seq=1 ttl=51 time=51.949 ms
64 bytes from 80.192.216.30: icmp_seq=2 ttl=51 time=51.142 ms
64 bytes from 80.192.216.30: icmp_seq=3 ttl=51 time=48.572 ms
64 bytes from 80.192.216.30: icmp_seq=4 ttl=51 time=52.226 ms
64 bytes from 80.192.216.30: icmp_seq=5 ttl=51 time=49.515 ms
64 bytes from 80.192.216.30: icmp_seq=6 ttl=51 time=48.849 ms
64 bytes from 80.192.216.30: icmp_seq=7 ttl=51 time=47.215 ms
64 bytes from 80.192.216.30: icmp_seq=8 ttl=51 time=53.368 ms
64 bytes from 80.192.216.30: icmp_seq=9 ttl=51 time=49.216 ms
64 bytes from 80.192.216.30: icmp_seq=10 ttl=51 time=49.857 ms
^C
--- 80.192.216.30 ping statistics ---
11 packets transmitted, 11 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 47.215/50.036/53.368/1.801 ms
ds2718@N0897-MAC ~ % redis-cli -h 80.192.216.30 -p 6379
^C%                                                                                                                                                                                                                 ds2718@N0897-MAC ~ % ping 80.192.216.30
PING 80.192.216.30 (80.192.216.30): 56 data bytes
64 bytes from 80.192.216.30: icmp_seq=0 ttl=51 time=55.590 ms
64 bytes from 80.192.216.30: icmp_seq=1 ttl=51 time=45.110 ms
64 bytes from 80.192.216.30: icmp_seq=2 ttl=51 time=49.660 ms
64 bytes from 80.192.216.30: icmp_seq=3 ttl=51 time=47.208 ms
64 bytes from 80.192.216.30: icmp_seq=4 ttl=51 time=128.200 ms
64 bytes from 80.192.216.30: icmp_seq=5 ttl=51 time=113.028 ms
64 bytes from 80.192.216.30: icmp_seq=6 ttl=51 time=173.964 ms
64 bytes from 80.192.216.30: icmp_seq=7 ttl=51 time=53.343 ms
^C
--- 80.192.216.30 ping statistics ---
8 packets transmitted, 8 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 45.110/83.263/173.964/45.659 ms
ds2718@N0897-MAC ~ % brew install rabbitmq
==> Downloading https://formulae.brew.sh/api/formula.jws.json
############################################################################################################################################################################################################# 100.0%
==> Downloading https://formulae.brew.sh/api/cask.jws.json
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/rabbitmq/manifests/4.0.2
############################################################################################################################################################################################################# 100.0%
==> Fetching dependencies for rabbitmq: m4, libtool, unixodbc, libtiff, wxwidgets and erlang
==> Downloading https://ghcr.io/v2/homebrew/core/m4/manifests/1.4.19
############################################################################################################################################################################################################# 100.0%
==> Fetching m4
==> Downloading https://ghcr.io/v2/homebrew/core/m4/blobs/sha256:f42d89db519a07d67bcaead6c8dfb2da45e8266bebb996dd8b3f19b1ca13b8a0
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libtool/manifests/2.5.3
############################################################################################################################################################################################################# 100.0%
==> Fetching libtool
==> Downloading https://ghcr.io/v2/homebrew/core/libtool/blobs/sha256:e857244e8cf19dd0d0005ab9ad0a3a180e61285dcb981fd6deda5c2e362d98cd
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/unixodbc/manifests/2.3.12
############################################################################################################################################################################################################# 100.0%
==> Fetching unixodbc
==> Downloading https://ghcr.io/v2/homebrew/core/unixodbc/blobs/sha256:4984c5ec2cd0ddc6393cfd60e42bc5748e3dc173750b74b2113de9b17c864c9a
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libtiff/manifests/4.7.0
############################################################################################################################################################################################################# 100.0%
==> Fetching libtiff
==> Downloading https://ghcr.io/v2/homebrew/core/libtiff/blobs/sha256:90bc1ab8734f27d41ceaeadc9e999de4c18766cf4b62e8fed1449dc828ea2395
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/wxwidgets/manifests/3.2.6
############################################################################################################################################################################################################# 100.0%
==> Fetching wxwidgets
==> Downloading https://ghcr.io/v2/homebrew/core/wxwidgets/blobs/sha256:3e24e13b0986b99ad7db4b72f7235403cf2eac9a6f8d6a8aff5242880f79153a
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/erlang/manifests/27.1.1
############################################################################################################################################################################################################# 100.0%
==> Fetching dependencies for erlang: ca-certificates
==> Downloading https://ghcr.io/v2/homebrew/core/ca-certificates/manifests/2024-09-24
############################################################################################################################################################################################################# 100.0%
==> Fetching ca-certificates
==> Downloading https://ghcr.io/v2/homebrew/core/ca-certificates/blobs/sha256:212f2576348d5f5797d8d3905eb70d0d9bf8829345bce9e20e2fd0336f344648
############################################################################################################################################################################################################# 100.0%
==> Fetching erlang
==> Downloading https://ghcr.io/v2/homebrew/core/erlang/blobs/sha256:ebf68c68967fc6ecb0105a2c03159f7c68bf7799b62b09edc95019d6dc895cd1
############################################################################################################################################################################################################# 100.0%
==> Fetching rabbitmq
==> Downloading https://ghcr.io/v2/homebrew/core/rabbitmq/blobs/sha256:4794f895c40aba9059928a0a96de46ebac51d80b39c4f8733ecd8211a4125743
############################################################################################################################################################################################################# 100.0%
==> Installing dependencies for rabbitmq: m4, libtool, unixodbc, libtiff, wxwidgets and erlang
==> Installing rabbitmq dependency: m4
==> Downloading https://ghcr.io/v2/homebrew/core/m4/manifests/1.4.19
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/5b2a7f715487b7377e409e8ca58569040cd89f33859f691210c58d94410fd33b--m4-1.4.19.bottle_manifest.json
==> Pouring m4--1.4.19.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/m4/1.4.19: 14 files, 728.7KB
==> Installing rabbitmq dependency: libtool
==> Downloading https://ghcr.io/v2/homebrew/core/libtool/manifests/2.5.3
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/a3fb370c644cf73593e4df8b5c40f2ccb0459d57248d95aba050def3c96414ad--libtool-2.5.3.bottle_manifest.json
==> Pouring libtool--2.5.3.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libtool/2.5.3: 76 files, 3.9MB
==> Installing rabbitmq dependency: unixodbc
==> Downloading https://ghcr.io/v2/homebrew/core/unixodbc/manifests/2.3.12
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/f0a48ea379f8e4acc3dc9d88ec4ce4e354b4437d2104efee3399b892b79d55ac--unixodbc-2.3.12.bottle_manifest.json
==> Pouring unixodbc--2.3.12.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/unixodbc/2.3.12: 48 files, 2.3MB
==> Installing rabbitmq dependency: libtiff
==> Downloading https://ghcr.io/v2/homebrew/core/libtiff/manifests/4.7.0
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/fcbf8df89b7dff054d1f02a8da056c581561fd44a924ae82139fd48a14b994b5--libtiff-4.7.0.bottle_manifest.json
==> Pouring libtiff--4.7.0.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libtiff/4.7.0: 486 files, 8.5MB
==> Installing rabbitmq dependency: wxwidgets
==> Downloading https://ghcr.io/v2/homebrew/core/wxwidgets/manifests/3.2.6
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/d7e746deddea8747a5b2a5cf3cafe3799515a322a45b2d3f45cee924e74fb761--wxwidgets-3.2.6.bottle_manifest.json
==> Pouring wxwidgets--3.2.6.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/wxwidgets/3.2.6: 836 files, 25.7MB
==> Installing rabbitmq dependency: erlang
==> Downloading https://ghcr.io/v2/homebrew/core/erlang/manifests/27.1.1
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/4145a34286df56577692eece65fcf97cee672afea3fd0f6ca5b1a021fba4842f--erlang-27.1.1.bottle_manifest.json
==> Installing dependencies for erlang: ca-certificates
==> Installing erlang dependency: ca-certificates
==> Downloading https://ghcr.io/v2/homebrew/core/ca-certificates/manifests/2024-09-24
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/338dad7c2ff7c822cda7c417944521589856741c0fbd7a7f07b88a18d7fb7e05--ca-certificates-2024-09-24.bottle_manifest.json
==> Pouring ca-certificates--2024-09-24.all.bottle.tar.gz
==> Regenerating CA certificate bundle from keychain, this may take a while...
🍺  /opt/homebrew/Cellar/ca-certificates/2024-09-24: 4 files, 237.4KB
==> Installing erlang
==> Pouring erlang--27.1.1.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/erlang/27.1.1: 8,621 files, 345.7MB
==> Installing rabbitmq
==> Pouring rabbitmq--4.0.2.all.bottle.tar.gz
==> Caveats
Management UI: http://localhost:15672
Homebrew-specific docs: https://rabbitmq.com/install-homebrew.html

To start rabbitmq now and restart at login:
  brew services start rabbitmq
Or, if you don't want/need a background service you can just run:
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
==> Summary
🍺  /opt/homebrew/Cellar/rabbitmq/4.0.2: 1,519 files, 35.7MB
==> Running `brew cleanup rabbitmq`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Upgrading 3 dependents of upgraded formulae:
Disable this behaviour by setting HOMEBREW_NO_INSTALLED_DEPENDENTS_CHECK.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
openssh 9.8p1 -> 9.9p1, python@3.12 3.12.6 -> 3.12.7, redis 7.2.5 -> 7.2.6
==> Downloading https://ghcr.io/v2/homebrew/core/python/3.12/manifests/3.12.7
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/openssh/manifests/9.9p1
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/redis/manifests/7.2.6
############################################################################################################################################################################################################# 100.0%
==> Checking for dependents of upgraded formulae...
==> No broken dependents found!
==> Caveats
==> rabbitmq
Management UI: http://localhost:15672
Homebrew-specific docs: https://rabbitmq.com/install-homebrew.html

To start rabbitmq now and restart at login:
  brew services start rabbitmq
Or, if you don't want/need a background service you can just run:
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
ds2718@N0897-MAC ~ % brew info rabbitmq
==> rabbitmq: stable 4.0.2 (bottled)
Messaging and streaming broker
https://www.rabbitmq.com
Installed
/opt/homebrew/Cellar/rabbitmq/4.0.2 (1,519 files, 35.7MB) *
  Poured from bottle using the formulae.brew.sh API on 2024-10-04 at 11:56:29
From: https://github.com/Homebrew/homebrew-core/blob/HEAD/Formula/r/rabbitmq.rb
License: MPL-2.0
==> Dependencies
Required: erlang ✔
==> Caveats
Management UI: http://localhost:15672
Homebrew-specific docs: https://rabbitmq.com/install-homebrew.html

To start rabbitmq now and restart at login:
  brew services start rabbitmq
Or, if you don't want/need a background service you can just run:
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
==> Analytics
install: 5,981 (30 days), 18,189 (90 days), 76,215 (365 days)
install-on-request: 5,983 (30 days), 18,190 (90 days), 76,214 (365 days)
build-error: 0 (30 days)
ds2718@N0897-MAC ~ % brew services start rabbitmq
==> Successfully started `rabbitmq` (label: homebrew.mxcl.rabbitmq)
ds2718@N0897-MAC ~ % rabbitmq info
zsh: command not found: rabbitmq
ds2718@N0897-MAC ~ % brew services start rabbitmq | grep conf
ds2718@N0897-MAC ~ % brew info rabbitmq | grep conf
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
ds2718@N0897-MAC ~ % vim /opt/homebrew/etc/rabbitmq/rabbitmq-env.conf
ds2718@N0897-MAC ~ % rabbitmq-server
=INFO REPORT==== 4-Oct-2024::12:07:07.831308 ===
    alarm_handler: {set,{system_memory_high_watermark,[]}}

BOOT FAILED
2024-10-04 12:07:12.934904+01:00 [error] <0.136.0> 
2024-10-04 12:07:12.934904+01:00 [error] <0.136.0> BOOT FAILED
2024-10-04 12:07:12.934904+01:00 [error] <0.136.0> ===========
2024-10-04 12:07:12.934904+01:00 [error] <0.136.0> ERROR: could not bind to distribution port 25672, it is in use by another node: rabbit@localhost
2024-10-04 12:07:12.934904+01:00 [error] <0.136.0> 
===========
ERROR: could not bind to distribution port 25672, it is in use by another node: rabbit@localhost

2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>     supervisor: {local,rabbit_prelaunch_sup}
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>     errorContext: start_error
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>     reason: {dist_port_already_used,25672,"rabbit","localhost"}
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>     offender: [{pid,undefined},
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>                {id,prelaunch},
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>                {mfargs,{rabbit_prelaunch,run_prelaunch_first_phase,[]}},
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>                {restart_type,transient},
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>                {significant,false},
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>                {shutdown,5000},
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0>                {child_type,worker}]
2024-10-04 12:07:13.941250+01:00 [error] <0.136.0> 
2024-10-04 12:07:13.942027+01:00 [notice] <0.45.0> Application rabbitmq_prelaunch exited with reason: {{shutdown,{failed_to_start_child,prelaunch,{dist_port_already_used,25672,"rabbit","localhost"}}},{rabbit_prelaunch_app,start,[normal,[]]}}
{exit,terminating,[{application_controller,call,2,[{file,"application_controller.erl"},{line,511}]},{application,'-ensure_all_started/3-lc$^0/1-0-',1,[{file,"application.erl"},{line,367}]},{application,ensure_all_started,3,[{file,"application.erl"},{line,367}]},{rabbit,'-start_it/1-fun-0-',1,[{file,"rabbit.erl"},{line,421}]},{timer,tc,2,[{file,"timer.erl"},{line,590}]},{rabbit,start_it,1,[{file,"rabbit.erl"},{line,419}]},{init,start_it,1,[]},{init,start_em,1,[]}]}
Runtime terminating during boot (terminating)

Crash dump is being written to: erl_crash.dump...done
[os_mon] cpu supervisor port (cpu_sup): Erlang has closed
[os_mon] memory supervisor port (memsup): Erlang has closed
ds2718@N0897-MAC ~ % rabbitmq-cli
zsh: command not found: rabbitmq-cli
ds2718@N0897-MAC ~ % rabbitmq    
zsh: command not found: rabbitmq
ds2718@N0897-MAC ~ % brew info rabbitmq
==> rabbitmq: stable 4.0.2 (bottled)
Messaging and streaming broker
https://www.rabbitmq.com
Installed
/opt/homebrew/Cellar/rabbitmq/4.0.2 (1,519 files, 35.7MB) *
  Poured from bottle using the formulae.brew.sh API on 2024-10-04 at 11:56:29
From: https://github.com/Homebrew/homebrew-core/blob/HEAD/Formula/r/rabbitmq.rb
License: MPL-2.0
==> Dependencies
Required: erlang ✔
==> Caveats
Management UI: http://localhost:15672
Homebrew-specific docs: https://rabbitmq.com/install-homebrew.html

To restart rabbitmq after an upgrade:
  brew services restart rabbitmq
Or, if you don't want/need a background service you can just run:
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
==> Analytics
install: 5,981 (30 days), 18,189 (90 days), 76,215 (365 days)
install-on-request: 5,983 (30 days), 18,190 (90 days), 76,214 (365 days)
build-error: 0 (30 days)
ds2718@N0897-MAC ~ % /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
=INFO REPORT==== 4-Oct-2024::12:09:47.286148 ===
    alarm_handler: {set,{system_memory_high_watermark,[]}}

BOOT FAILED
===========
ERROR: could not bind to distribution port 25672, it is in use by another node: rabbit@localhost
2024-10-04 12:09:52.383308+01:00 [error] <0.136.0> 
2024-10-04 12:09:52.383308+01:00 [error] <0.136.0> BOOT FAILED
2024-10-04 12:09:52.383308+01:00 [error] <0.136.0> ===========
2024-10-04 12:09:52.383308+01:00 [error] <0.136.0> ERROR: could not bind to distribution port 25672, it is in use by another node: rabbit@localhost
2024-10-04 12:09:52.383308+01:00 [error] <0.136.0> 

2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>     supervisor: {local,rabbit_prelaunch_sup}
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>     errorContext: start_error
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>     reason: {dist_port_already_used,25672,"rabbit","localhost"}
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>     offender: [{pid,undefined},
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>                {id,prelaunch},
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>                {mfargs,{rabbit_prelaunch,run_prelaunch_first_phase,[]}},
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>                {restart_type,transient},
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>                {significant,false},
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>                {shutdown,5000},
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0>                {child_type,worker}]
2024-10-04 12:09:53.389384+01:00 [error] <0.136.0> 
{exit,2024-10-04 12:09:53.389873+01:00 [notice] <0.45.0> Application rabbitmq_prelaunch exited with reason: {{shutdown,{failed_to_start_child,prelaunch,{dist_port_already_used,25672,"rabbit","localhost"}}},{rabbit_prelaunch_app,start,[normal,[]]}}
terminating,[{application_controller,call,2,[{file,"application_controller.erl"},{line,511}]},{application,'-ensure_all_started/3-lc$^0/1-0-',1,[{file,"application.erl"},{line,367}]},{application,ensure_all_started,3,[{file,"application.erl"},{line,367}]},{rabbit,'-start_it/1-fun-0-',1,[{file,"rabbit.erl"},{line,421}]},{timer,tc,2,[{file,"timer.erl"},{line,590}]},{rabbit,start_it,1,[{file,"rabbit.erl"},{line,419}]},{init,start_it,1,[]},{init,start_em,1,[]}]}
Runtime terminating during boot (terminating)

Crash dump is being written to: erl_crash.dump...done
[os_mon] cpu supervisor port (cpu_sup): Erlang has closed
[os_mon] memory supervisor port (memsup): Erlang has closed
ds2718@N0897-MAC ~ % brew info rabbitmq | grep conf                  
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
ds2718@N0897-MAC ~ % rabbitmq-diagnostics status
Status of node rabbit@localhost ...
Runtime

OS PID: 80355
OS: macOS
Uptime (seconds): 802
Is under maintenance?: false
RabbitMQ version: 4.0.2
RabbitMQ release series support status: see https://www.rabbitmq.com/release-information
Node name: rabbit@localhost
Erlang configuration: Erlang/OTP 27 [erts-15.1.1] [source] [64-bit] [smp:8:8] [ds:8:8:10] [async-threads:1] [jit] [dtrace]
Crypto library: OpenSSL 3.3.2 3 Sep 2024
Erlang processes: 471 used, 1048576 limit
Scheduler run queue: 1
Cluster heartbeat timeout (net_ticktime): 60

Plugins

Enabled plugin file: /opt/homebrew/etc/rabbitmq/enabled_plugins
Enabled plugins:

 * rabbitmq_mqtt
 * rabbitmq_stream
 * rabbitmq_stomp
 * rabbitmq_stream_common
 * rabbitmq_amqp1_0
 * rabbitmq_management
 * rabbitmq_management_agent
 * rabbitmq_web_dispatch
 * amqp_client
 * cowboy
 * cowlib
 * oauth2_client
 * jose

Data directory

Node data directory: /opt/homebrew/var/lib/rabbitmq/mnesia/rabbit@localhost
Raft data directory: /opt/homebrew/var/lib/rabbitmq/mnesia/rabbit@localhost/quorum/rabbit@localhost

Config files


Log file(s)

 * /opt/homebrew/var/log/rabbitmq/rabbit@localhost.log
 * <stdout>

Alarms

(none)

Memory

Total memory used: 0.0437 gb
Calculation strategy: rss
Memory high watermark setting: 0.6 of available memory, computed to: 5.154 gb

other_system: 0.0208 gb (29.14 %)
code: 0.0205 gb (28.67 %)
other_proc: 0.0166 gb (23.24 %)
allocated_unused: 0.0065 gb (9.05 %)
other_ets: 0.0023 gb (3.19 %)
plugins: 0.0018 gb (2.48 %)
metrics: 0.0012 gb (1.71 %)
atom: 0.0011 gb (1.58 %)
msg_index: 0.0002 gb (0.32 %)
mgmt_db: 0.0002 gb (0.22 %)
metadata_store: 0.0001 gb (0.12 %)
mnesia: 0.0001 gb (0.1 %)
binary: 0.0001 gb (0.1 %)
quorum_ets: 0.0 gb (0.04 %)
metadata_store_ets: 0.0 gb (0.01 %)
connection_other: 0.0 gb (0.0 %)
quorum_queue_procs: 0.0 gb (0.0 %)
quorum_queue_dlx_procs: 0.0 gb (0.0 %)
stream_queue_procs: 0.0 gb (0.0 %)
stream_queue_replica_reader_procs: 0.0 gb (0.0 %)
connection_readers: 0.0 gb (0.0 %)
connection_writers: 0.0 gb (0.0 %)
connection_channels: 0.0 gb (0.0 %)
queue_procs: 0.0 gb (0.0 %)
stream_queue_coordinator_procs: 0.0 gb (0.0 %)
reserved_unallocated: 0.0 gb (0.0 %)

File Descriptors

Total: 0, limit: 159

Free Disk Space

Low free disk space watermark: 0.05 gb
Free disk space: 425.2784 gb

Totals

Connection count: 0
Queue count: 0
Virtual host count: 1

Listeners

Interface: [::], port: 15672, protocol: http, purpose: HTTP API
Interface: [::], port: 61613, protocol: stomp, purpose: STOMP
Interface: [::], port: 5552, protocol: stream, purpose: stream
Interface: [::], port: 1883, protocol: mqtt, purpose: MQTT
Interface: [::], port: 25672, protocol: clustering, purpose: inter-node and CLI tool communication
Interface: 127.0.0.1, port: 5672, protocol: amqp, purpose: AMQP 0-9-1 and AMQP 1.0
ds2718@N0897-MAC ~ % brew uninstall rabbitmq
Uninstalling /opt/homebrew/Cellar/rabbitmq/4.0.2... (1,519 files, 35.7MB)

Warning: The following rabbitmq configuration files have not been removed!
If desired, remove them manually with `rm -rf`:
  /opt/homebrew/etc/rabbitmq
  /opt/homebrew/etc/rabbitmq/enabled_plugins
  /opt/homebrew/etc/rabbitmq/rabbitmq-env.conf
==> Autoremoving 6 unneeded formulae:
erlang
libtiff
libtool
m4
unixodbc
wxwidgets
Uninstalling /opt/homebrew/Cellar/erlang/27.1.1... (8,621 files, 345.7MB)
Uninstalling /opt/homebrew/Cellar/wxwidgets/3.2.6... (836 files, 25.7MB)
Uninstalling /opt/homebrew/Cellar/unixodbc/2.3.12... (48 files, 2.3MB)
Uninstalling /opt/homebrew/Cellar/libtiff/4.7.0... (486 files, 8.5MB)
Uninstalling /opt/homebrew/Cellar/libtool/2.5.3... (76 files, 3.9MB)
Uninstalling /opt/homebrew/Cellar/m4/1.4.19... (14 files, 728.7KB)
ds2718@N0897-MAC ~ % brew install rabbitmq      
==> Downloading https://formulae.brew.sh/api/formula.jws.json
############################################################################################################################################################################################################# 100.0%
==> Downloading https://formulae.brew.sh/api/cask.jws.json
############################################################################################################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/rabbitmq/manifests/4.0.2
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/08173c7fcaf54727cddb89560a9ac7a1e16cae8c69d447baac8456c09ff88ad8--rabbitmq-4.0.2.bottle_manifest.json
==> Fetching dependencies for rabbitmq: m4, libtool, unixodbc, libtiff, wxwidgets and erlang
==> Downloading https://ghcr.io/v2/homebrew/core/m4/manifests/1.4.19
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/5b2a7f715487b7377e409e8ca58569040cd89f33859f691210c58d94410fd33b--m4-1.4.19.bottle_manifest.json
==> Fetching m4
==> Downloading https://ghcr.io/v2/homebrew/core/m4/blobs/sha256:f42d89db519a07d67bcaead6c8dfb2da45e8266bebb996dd8b3f19b1ca13b8a0
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/943052706ee3b934ae9cf355e827619bbe1f44764123c7e7cce4efde11c24b28--m4--1.4.19.arm64_sonoma.bottle.tar.gz
==> Downloading https://ghcr.io/v2/homebrew/core/libtool/manifests/2.5.3
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/a3fb370c644cf73593e4df8b5c40f2ccb0459d57248d95aba050def3c96414ad--libtool-2.5.3.bottle_manifest.json
==> Fetching libtool
==> Downloading https://ghcr.io/v2/homebrew/core/libtool/blobs/sha256:e857244e8cf19dd0d0005ab9ad0a3a180e61285dcb981fd6deda5c2e362d98cd
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/c0c14fae3a05136048cb3a85735d4a2d8b4d9cc28a74e2bd880da09a9b0e188a--libtool--2.5.3.arm64_sonoma.bottle.tar.gz
==> Downloading https://ghcr.io/v2/homebrew/core/unixodbc/manifests/2.3.12
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/f0a48ea379f8e4acc3dc9d88ec4ce4e354b4437d2104efee3399b892b79d55ac--unixodbc-2.3.12.bottle_manifest.json
==> Fetching unixodbc
==> Downloading https://ghcr.io/v2/homebrew/core/unixodbc/blobs/sha256:4984c5ec2cd0ddc6393cfd60e42bc5748e3dc173750b74b2113de9b17c864c9a
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/94e47cf873d0b521f547c75b6a03c8558439d12c33deba691ff47e92385edb73--unixodbc--2.3.12.arm64_sonoma.bottle.tar.gz
==> Downloading https://ghcr.io/v2/homebrew/core/libtiff/manifests/4.7.0
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/fcbf8df89b7dff054d1f02a8da056c581561fd44a924ae82139fd48a14b994b5--libtiff-4.7.0.bottle_manifest.json
==> Fetching libtiff
==> Downloading https://ghcr.io/v2/homebrew/core/libtiff/blobs/sha256:90bc1ab8734f27d41ceaeadc9e999de4c18766cf4b62e8fed1449dc828ea2395
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/444d5ef14225728eb86cef7c17778652b99836274c06ace0e256e87cbd231d2e--libtiff--4.7.0.arm64_sonoma.bottle.tar.gz
==> Downloading https://ghcr.io/v2/homebrew/core/wxwidgets/manifests/3.2.6
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/d7e746deddea8747a5b2a5cf3cafe3799515a322a45b2d3f45cee924e74fb761--wxwidgets-3.2.6.bottle_manifest.json
==> Fetching wxwidgets
==> Downloading https://ghcr.io/v2/homebrew/core/wxwidgets/blobs/sha256:3e24e13b0986b99ad7db4b72f7235403cf2eac9a6f8d6a8aff5242880f79153a
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/efcaf7dcd734f99a9b60238455530d649b0dbe9ad104310e3f023d74d8df6cb4--wxwidgets--3.2.6.arm64_sonoma.bottle.tar.gz
==> Downloading https://ghcr.io/v2/homebrew/core/erlang/manifests/27.1.1
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/4145a34286df56577692eece65fcf97cee672afea3fd0f6ca5b1a021fba4842f--erlang-27.1.1.bottle_manifest.json
==> Fetching erlang
==> Downloading https://ghcr.io/v2/homebrew/core/erlang/blobs/sha256:ebf68c68967fc6ecb0105a2c03159f7c68bf7799b62b09edc95019d6dc895cd1
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/1c3383714b9203400fca1cb818933d0c2af4914cf3f8654a1a37ee0ce2749e1c--erlang--27.1.1.arm64_sonoma.bottle.tar.gz
==> Fetching rabbitmq
==> Downloading https://ghcr.io/v2/homebrew/core/rabbitmq/blobs/sha256:4794f895c40aba9059928a0a96de46ebac51d80b39c4f8733ecd8211a4125743
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/1d7d6249f4d01bf2f7d7022b860a0ea941b5e1d9d54223a0d6c2fde106e4338f--rabbitmq--4.0.2.all.bottle.tar.gz
==> Installing dependencies for rabbitmq: m4, libtool, unixodbc, libtiff, wxwidgets and erlang
==> Installing rabbitmq dependency: m4
==> Downloading https://ghcr.io/v2/homebrew/core/m4/manifests/1.4.19
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/5b2a7f715487b7377e409e8ca58569040cd89f33859f691210c58d94410fd33b--m4-1.4.19.bottle_manifest.json
==> Pouring m4--1.4.19.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/m4/1.4.19: 14 files, 728.7KB
==> Installing rabbitmq dependency: libtool
==> Downloading https://ghcr.io/v2/homebrew/core/libtool/manifests/2.5.3
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/a3fb370c644cf73593e4df8b5c40f2ccb0459d57248d95aba050def3c96414ad--libtool-2.5.3.bottle_manifest.json
==> Pouring libtool--2.5.3.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libtool/2.5.3: 76 files, 3.9MB
==> Installing rabbitmq dependency: unixodbc
==> Downloading https://ghcr.io/v2/homebrew/core/unixodbc/manifests/2.3.12
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/f0a48ea379f8e4acc3dc9d88ec4ce4e354b4437d2104efee3399b892b79d55ac--unixodbc-2.3.12.bottle_manifest.json
==> Pouring unixodbc--2.3.12.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/unixodbc/2.3.12: 48 files, 2.3MB
==> Installing rabbitmq dependency: libtiff
==> Downloading https://ghcr.io/v2/homebrew/core/libtiff/manifests/4.7.0
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/fcbf8df89b7dff054d1f02a8da056c581561fd44a924ae82139fd48a14b994b5--libtiff-4.7.0.bottle_manifest.json
==> Pouring libtiff--4.7.0.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/libtiff/4.7.0: 486 files, 8.5MB
==> Installing rabbitmq dependency: wxwidgets
==> Downloading https://ghcr.io/v2/homebrew/core/wxwidgets/manifests/3.2.6
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/d7e746deddea8747a5b2a5cf3cafe3799515a322a45b2d3f45cee924e74fb761--wxwidgets-3.2.6.bottle_manifest.json
==> Pouring wxwidgets--3.2.6.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/wxwidgets/3.2.6: 836 files, 25.7MB
==> Installing rabbitmq dependency: erlang
==> Downloading https://ghcr.io/v2/homebrew/core/erlang/manifests/27.1.1
Already downloaded: /Users/ds2718/Library/Caches/Homebrew/downloads/4145a34286df56577692eece65fcf97cee672afea3fd0f6ca5b1a021fba4842f--erlang-27.1.1.bottle_manifest.json
==> Pouring erlang--27.1.1.arm64_sonoma.bottle.tar.gz
🍺  /opt/homebrew/Cellar/erlang/27.1.1: 8,621 files, 345.7MB
==> Installing rabbitmq
==> Pouring rabbitmq--4.0.2.all.bottle.tar.gz
==> Caveats
Management UI: http://localhost:15672
Homebrew-specific docs: https://rabbitmq.com/install-homebrew.html

To restart rabbitmq after an upgrade:
  brew services restart rabbitmq
Or, if you don't want/need a background service you can just run:
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
==> Summary
🍺  /opt/homebrew/Cellar/rabbitmq/4.0.2: 1,519 files, 35.7MB
==> Running `brew cleanup rabbitmq`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Caveats
==> rabbitmq
Management UI: http://localhost:15672
Homebrew-specific docs: https://rabbitmq.com/install-homebrew.html

To restart rabbitmq after an upgrade:
  brew services restart rabbitmq
Or, if you don't want/need a background service you can just run:
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
ds2718@N0897-MAC ~ % brew services rabbitmq
Usage: brew services [subcommand]

Manage background services with macOS' launchctl(1) daemon manager or Linux's
systemctl(1) service manager.

If sudo is passed, operate on /Library/LaunchDaemons or
/usr/lib/systemd/system  (started at boot). Otherwise, operate on
~/Library/LaunchAgents or ~/.config/systemd/user (started at login).

[sudo] brew services [list] (--json) (--debug):
    List information about all managed services for the current user (or root).
Provides more output from Homebrew and launchctl(1) or systemctl(1) if run
with --debug.

[sudo] brew services info (formula|--all|--json):
    List all managed services for the current user (or root).

[sudo] brew services run (formula|--all):
    Run the service formula without registering to launch at login (or boot).

[sudo] brew services start (formula|--all|--file=):
    Start the service formula immediately and register it to launch at login
(or boot).

[sudo] brew services stop (formula|--all):
    Stop the service formula immediately and unregister it from launching at
login (or boot).

[sudo] brew services kill (formula|--all):
    Stop the service formula immediately but keep it registered to launch at
login (or boot).

[sudo] brew services restart (formula|--all):
    Stop (if necessary) and start the service formula immediately and register
it to launch at login (or boot).

[sudo] brew services cleanup:
    Remove all unused services.

      --file                       Use the service file from this location to
                                   start the service.
      --sudo-service-user          When run as root on macOS, run the service(s)
                                   as this user.
      --all                        Run subcommand on all services.
      --json                       Output as JSON.
      --no-wait                    Don't wait for stop to finish stopping the
                                   service.
  -d, --debug                      Display any debugging information.
  -q, --quiet                      Make some output more quiet.
  -v, --verbose                    Make some output more verbose.
  -h, --help                       Show this message.

Error: Invalid usage: unknown subcommand: `rabbitmq`
ds2718@N0897-MAC ~ % brew services start rabbitmq
Service `rabbitmq` already started, use `brew services restart rabbitmq` to restart.
ds2718@N0897-MAC ~ % brew services restart rabbitmq
Stopping `rabbitmq`... (might take a while)
==> Successfully stopped `rabbitmq` (label: homebrew.mxcl.rabbitmq)
==> Successfully started `rabbitmq` (label: homebrew.mxcl.rabbitmq)
ds2718@N0897-MAC ~ % brew info rabbitmq | grep conf 
  CONF_ENV_FILE="/opt/homebrew/etc/rabbitmq/rabbitmq-env.conf" /opt/homebrew/opt/rabbitmq/sbin/rabbitmq-server
ds2718@N0897-MAC ~ % vim /opt/homebrew/etc/rabbitmq/rabbitmq-env.conf
ds2718@N0897-MAC ~ % ls /opt/homebrew/etc/rabbitmq/rabbitmq
ls: /opt/homebrew/etc/rabbitmq/rabbitmq: No such file or directory
ds2718@N0897-MAC ~ % ls ~/opt/homebrew/etc/rabbitmq/rabbitmq
ls: /Users/ds2718/opt/homebrew/etc/rabbitmq/rabbitmq: No such file or directory
ds2718@N0897-MAC ~ % ls /opt/homebrew/etc/rabbitmq                
enabled_plugins		rabbitmq-env.conf
ds2718@N0897-MAC ~ % vim /opt/homebrew/etc/rabbitmq/rabbitmq-env.conf
ds2718@N0897-MAC ~ % vim /opt/homebrew/etc/rabbitmq/rabbitmq.conf    
ds2718@N0897-MAC ~ % rabbitmq-diagnosis status
zsh: command not found: rabbitmq-diagnosis
ds2718@N0897-MAC ~ % rabbitmq-diagnostics status                  
Status of node rabbit@localhost ...
Runtime

OS PID: 88809
OS: macOS
Uptime (seconds): 914
Is under maintenance?: false
RabbitMQ version: 4.0.2
RabbitMQ release series support status: see https://www.rabbitmq.com/release-information
Node name: rabbit@localhost
Erlang configuration: Erlang/OTP 27 [erts-15.1.1] [source] [64-bit] [smp:8:8] [ds:8:8:10] [async-threads:1] [jit] [dtrace]
Crypto library: OpenSSL 3.3.2 3 Sep 2024
Erlang processes: 470 used, 1048576 limit
Scheduler run queue: 1
Cluster heartbeat timeout (net_ticktime): 60

Plugins

Enabled plugin file: /opt/homebrew/etc/rabbitmq/enabled_plugins
Enabled plugins:

 * rabbitmq_mqtt
 * rabbitmq_stream
 * rabbitmq_stomp
 * rabbitmq_stream_common
 * rabbitmq_amqp1_0
 * rabbitmq_management
 * rabbitmq_management_agent
 * rabbitmq_web_dispatch
 * amqp_client
 * cowboy
 * cowlib
 * oauth2_client
 * jose

Data directory

Node data directory: /opt/homebrew/var/lib/rabbitmq/mnesia/rabbit@localhost
Raft data directory: /opt/homebrew/var/lib/rabbitmq/mnesia/rabbit@localhost/quorum/rabbit@localhost

Config files


Log file(s)

 * /opt/homebrew/var/log/rabbitmq/rabbit@localhost.log
 * <stdout>

Alarms

(none)

Memory

Total memory used: 0.0486 gb
Calculation strategy: rss
Memory high watermark setting: 0.6 of available memory, computed to: 5.154 gb

other_system: 0.0198 gb (27.28 %)
code: 0.0196 gb (27.07 %)
other_proc: 0.0164 gb (22.62 %)
allocated_unused: 0.0095 gb (13.09 %)
other_ets: 0.0022 gb (3.09 %)
plugins: 0.002 gb (2.7 %)
metrics: 0.0012 gb (1.69 %)
atom: 0.0011 gb (1.49 %)
msg_index: 0.0002 gb (0.31 %)
mgmt_db: 0.0002 gb (0.22 %)
metadata_store: 0.0001 gb (0.17 %)
binary: 0.0001 gb (0.1 %)
mnesia: 0.0001 gb (0.1 %)
quorum_ets: 0.0 gb (0.04 %)
metadata_store_ets: 0.0 gb (0.01 %)
connection_other: 0.0 gb (0.0 %)
quorum_queue_procs: 0.0 gb (0.0 %)
quorum_queue_dlx_procs: 0.0 gb (0.0 %)
stream_queue_procs: 0.0 gb (0.0 %)
stream_queue_replica_reader_procs: 0.0 gb (0.0 %)
connection_readers: 0.0 gb (0.0 %)
connection_writers: 0.0 gb (0.0 %)
connection_channels: 0.0 gb (0.0 %)
queue_procs: 0.0 gb (0.0 %)
stream_queue_coordinator_procs: 0.0 gb (0.0 %)
reserved_unallocated: 0.0 gb (0.0 %)

File Descriptors

Total: 0, limit: 159

Free Disk Space

Low free disk space watermark: 0.05 gb
Free disk space: 425.2632 gb

Totals

Connection count: 0
Queue count: 0
Virtual host count: 1

Listeners

Interface: [::], port: 15672, protocol: http, purpose: HTTP API
Interface: [::], port: 61613, protocol: stomp, purpose: STOMP
Interface: [::], port: 5552, protocol: stream, purpose: stream
Interface: [::], port: 1883, protocol: mqtt, purpose: MQTT
Interface: [::], port: 25672, protocol: clustering, purpose: inter-node and CLI tool communication
Interface: 127.0.0.1, port: 5672, protocol: amqp, purpose: AMQP 0-9-1 and AMQP 1.0
ds2718@N0897-MAC ~ % netstat -ltn | grep rabbitmq
ds2718@N0897-MAC ~ % netstat -rn\ | grep rabbitmq
netstat: illegal option --  
Usage:	netstat [-AaLlnW] [-f address_family | -p protocol]
	netstat [-gilns] [-f address_family]
	netstat -i | -I interface [-w wait] [-abdgRtS]
	netstat -s [-s] [-f address_family | -p protocol] [-w wait]
	netstat -i | -I interface -s [-f address_family | -p protocol]
	netstat -m [-m]
	netstat -r [-Aaln] [-f address_family]
	netstat -rs [-s]

ds2718@N0897-MAC ~ % netstat -rn | grep rabbitmq 
ds2718@N0897-MAC ~ % netstat -r | grep rabbitmq 
^C
ds2718@N0897-MAC ~ % vim /opt/homebrew/etc/rabbitmq/rabbitmq.conf
ds2718@N0897-MAC ~ % vim /opt/homebrew/etc/rabbitmq/rabbitmq-env.conf
\%                                                                                                                                                                                                                  ds2718@N0897-MAC ~ % netstat -an | grep 5672
tcp4       0      0  127.0.0.1.5672         *.*                    LISTEN     
tcp4       0      0  *.15672                *.*                    LISTEN     
tcp4       0      0  *.25672                *.*                    LISTEN     
ds2718@N0897-MAC ~ % sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setglobalstate off

Password:
Firewall is disabled. (State = 0)
ds2718@N0897-MAC ~ % ifconfig
lo0: flags=8049<UP,LOOPBACK,RUNNING,MULTICAST> mtu 16384
	options=1203<RXCSUM,TXCSUM,TXSTATUS,SW_TIMESTAMP>
	inet 127.0.0.1 netmask 0xff000000
	inet6 ::1 prefixlen 128 
	inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1 
	nd6 options=201<PERFORMNUD,DAD>
gif0: flags=8010<POINTOPOINT,MULTICAST> mtu 1280
stf0: flags=0<> mtu 1280
anpi0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether fe:de:59:8d:a8:e6
	media: none
	status: inactive
anpi1: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether fe:de:59:8d:a8:e7
	media: none
	status: inactive
en3: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether fe:de:59:8d:a8:c6
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
en5: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether fe:de:59:8d:a8:c7
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
en1: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=460<TSO4,TSO6,CHANNEL_IO>
	ether 36:71:f9:5a:c4:c0
	media: autoselect <full-duplex>
	status: inactive
en2: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=460<TSO4,TSO6,CHANNEL_IO>
	ether 36:71:f9:5a:c4:c4
	media: autoselect <full-duplex>
	status: inactive
bridge0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=63<RXCSUM,TXCSUM,TSO4,TSO6>
	ether 36:71:f9:5a:c4:c0
	Configuration:
		id 0:0:0:0:0:0 priority 0 hellotime 0 fwddelay 0
		maxage 0 holdcnt 0 proto stp maxaddr 100 timeout 1200
		root id 0:0:0:0:0:0 priority 0 ifcost 0 port 0
		ipfilter disabled flags 0x0
	member: en1 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 8 priority 0 path cost 0
	member: en2 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 9 priority 0 path cost 0
	nd6 options=201<PERFORMNUD,DAD>
	media: <unknown type>
	status: inactive
ap1: flags=8843<UP,BROADCAST,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6460<TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether 32:9f:41:af:8b:cb
	inet6 fe80::309f:41ff:feaf:8bcb%ap1 prefixlen 64 scopeid 0xb 
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect (<unknown type>)
	status: inactive
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6460<TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether 10:9f:41:af:8b:cb
	inet6 fe80::103c:d995:1fc9:4659%en0 prefixlen 64 secured scopeid 0xc 
	inet 192.168.0.66 netmask 0xffffff00 broadcast 192.168.0.255
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
awdl0: flags=8843<UP,BROADCAST,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6460<TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether 4e:89:dd:7d:54:bd
	inet6 fe80::4c89:ddff:fe7d:54bd%awdl0 prefixlen 64 scopeid 0xd 
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
llw0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 4e:89:dd:7d:54:bd
	inet6 fe80::4c89:ddff:fe7d:54bd%llw0 prefixlen 64 scopeid 0xe 
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: inactive
utun0: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1500
	inet6 fe80::cf72:7b13:c6a0:75fa%utun0 prefixlen 64 scopeid 0xf 
	nd6 options=201<PERFORMNUD,DAD>
utun1: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1380
	inet6 fe80::30df:f0b3:b889:4261%utun1 prefixlen 64 scopeid 0x10 
	nd6 options=201<PERFORMNUD,DAD>
utun2: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 2000
	inet6 fe80::8530:ea20:c5a:4ef2%utun2 prefixlen 64 scopeid 0x11 
	nd6 options=201<PERFORMNUD,DAD>
utun3: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1000
	inet6 fe80::ce81:b1c:bd2c:69e%utun3 prefixlen 64 scopeid 0x12 
	nd6 options=201<PERFORMNUD,DAD>
en4: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6464<VLAN_MTU,TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether 84:3a:5b:3a:c1:6e
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect (none)
	status: inactive
ds2718@N0897-MAC ~ % ifconfig | grep 192
	inet 192.168.0.66 netmask 0xffffff00 broadcast 192.168.0.255
ds2718@N0897-MAC ~ % curl ifconfig.me
80.192.216.30%                                                                                                                                                                                                      ds2718@N0897-MAC ~ % cd .ssh
ds2718@N0897-MAC .ssh % ls
config		id_ed25519	id_ed25519.pub	known_hosts	known_hosts.old	vm_password.txt
ds2718@N0897-MAC .ssh % vim known_hosts
ds2718@N0897-MAC .ssh % vim id_ed25519
ds2718@N0897-MAC .ssh % vim known_hosts.old
ds2718@N0897-MAC .ssh % vim config         
ds2718@N0897-MAC .ssh % netstat -an | grep 5672                                                  
tcp4       0      0  127.0.0.1.5672         *.*                    LISTEN     
tcp4       0      0  *.15672                *.*                    LISTEN     
tcp4       0      0  *.25672                *.*                    LISTEN     
ds2718@N0897-MAC .ssh % brew services restart rabbitmq
Stopping `rabbitmq`... (might take a while)
==> Successfully stopped `rabbitmq` (label: homebrew.mxcl.rabbitmq)
==> Successfully started `rabbitmq` (label: homebrew.mxcl.rabbitmq)
ds2718@N0897-MAC .ssh % netstat -an | grep 5672 
tcp4       0      0  *.25672                *.*                    LISTEN     
ds2718@N0897-MAC .ssh % rabbitmq-plugins enable rabbitmq_management
Enabling plugins on node rabbit@localhost:
rabbitmq_management
The following plugins have been configured:
  rabbitmq_amqp1_0
  rabbitmq_management
  rabbitmq_management_agent
  rabbitmq_mqtt
  rabbitmq_stomp
  rabbitmq_stream
  rabbitmq_web_dispatch
Applying plugin configuration to rabbit@localhost...
Plugin configuration unchanged.
ds2718@N0897-MAC .ssh % rabbitmq add_user khalid reg
zsh: command not found: rabbitmq
ds2718@N0897-MAC .ssh % rabbitmqctl add_user khalid reg
Adding user "khalid" ...
Done. Don't forget to grant the user permissions to some virtual hosts! See 'rabbitmqctl help set_permissions' to learn more.
ds2718@N0897-MAC .ssh % rabbitmqctl set_user_tags khalid administrator
Setting tags for user "khalid" to [administrator] ...
ds2718@N0897-MAC .ssh % rabbitmqctl help set_permissions 

Usage

rabbitmqctl [--node <node>] [--longnames] [--quiet] set_permissions [--vhost <vhost>] <username> <conf> <write> <read>

Sets user permissions for a vhost.


Arguments and Options

<username>
	Self-explanatory

<conf>
	Configuration permission pattern

<write>
	Write permission pattern

<read>
	Read permission pattern


Relevant Doc Guides

 * https://rabbitmq.com/docs/access-control/

 * https://rabbitmq.com/docs/vhosts/


General Options

The following options are accepted by most or all commands.

short            | long          | description
-----------------|---------------|--------------------------------
-?               | --help        | displays command help
-n <node>        | --node <node> | connect to node <node>
-l               | --longnames   | use long host names
-t               | --timeout <n> | for commands that support it, operation timeout in seconds
-q               | --quiet       | suppress informational messages
-s               | --silent      | suppress informational messages
                                 | and table header row
-p               | --vhost       | for commands that are scoped to a virtual host,
                 |               | virtual host to use
                 | --formatter   | alternative result formatter to use
                                 | if supported: json, pretty_table, table, csv, erlang
                                   not all commands support all (or any) alternative formatters.

ds2718@N0897-MAC .ssh % rabbitmqctl set_permissions -p / khalid ".*" ".*" ".*"
Setting permissions for user "khalid" in vhost "/" ...
ds2718@N0897-MAC .ssh % ls
config		id_ed25519	id_ed25519.pub	known_hosts	known_hosts.old	vm_password.txt
ds2718@N0897-MAC .ssh % cd 
ds2718@N0897-MAC ~ % vim /opt/homebrew/etc/rabbitmq/rabbitmq-env.conf
ds2718@N0897-MAC ~ % vim /opt/homebrew/etc/rabbitmq/rabbitmq.conf    
ds2718@N0897-MAC ~ % brew services start redis
==> Successfully started `redis` (label: homebrew.mxcl.redis)
ds2718@N0897-MAC ~ % ssh csd3

        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>
        <>                                                        <>
        <>                        !WARNING!                       <>
        <>                                                        <>
        <>                    RCS CSD3 Facility                   <>
        <>             Unauthorised Access Prohibited             <>
        <>    Use of this system constitutes acceptance of our    <>
        <>                     policies - see                     <>
        <> http://docs.hpc.cam.ac.uk/hpc/user-guide/policies.html <>
        <>                                                        <>
        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>


(ir-lawa1@login-icelake.hpc.cam.ac.uk) TOTP Verification Code: 587155
Last login: Mon Oct  7 12:16:36 2024 from 194.81.236.242
[ir-lawa1@login-q-3 ~]$ ls
rds  slurm_submit.peta4-cclake  slurm_submit.peta4-icelake  slurm_submit.wilkes3
[ir-lawa1@login-q-3 ~]$ cd rds
[ir-lawa1@login-q-3 rds]$ ls
rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-3 rds]$ ls rds-ukaea-ap002-mOlK9qn0PlQ
Ansys           ir-atki2  ir-byer1  ir-cumm2        ir-erka2-v2312  ir-horn3  ir-lahi1  ir-lykk1  ir-mars5  ir-nunn1  ir-pame1  ir-plow1  ir-sash1  ir-swan1  ir-turk1  ir-zani1    slurm-28064302.out
CRAsimulations  ir-bhat1  ir-care1  ir-edge2        ir-gadg1        ir-jack5  ir-lan1   ir-ma1    ir-maso4  ir-osbo2  ir-park1  ir-quan1  ir-shan1  ir-tind1  ir-wall2  mast        tab53
dc-davi4        ir-bren1  ir-cast3  ir-erka2-10     ir-harr6        ir-kerr2  ir-lawa1  ir-mage1  ir-miji1  ir-otin1  ir-parr3  ir-rath2  ir-sidd1  ir-tiru1  ir-watt2  mast-adios  uda-install
ir-armi3        ir-broo2  ir-chap2  ir-erka2-v2306  ir-hold2        ir-kryj2  ir-lewi4  ir-mant2  ir-nobr1  ir-oztu1  ir-pate3  ir-real1  ir-stef1  ir-tolk1  ir-whit7  raptor      ukaea-farscape
[ir-lawa1@login-q-3 rds]$ cd rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-3 rds-ukaea-ap002-mOlK9qn0PlQ]$ cd ir-lawa1
[ir-lawa1@login-q-3 ir-lawa1]$ ls
airflow_test  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-3 ir-lawa1]$ vim rabbitmq_conn.py
[ir-lawa1@login-q-2 airflow_test]$ vim airflow.cfg
[ir-lawa1@login-q-2 airflow_test]$ vim -n airflow.cfg
[ir-lawa1@login-q-2 airflow_test]$ airflow db int
-bash: airflow: command not found
[ir-lawa1@login-q-2 airflow_test]$ Read from remote host login-icelake.hpc.cam.ac.uk: Operation timed out
Connection to login-icelake.hpc.cam.ac.uk closed.
client_loop: send disconnect: Broken pipe
ds2718@N0897-MAC ~ % curl ifconfig.me
194.81.236.242%                                                                                                                                                                                                       ds2718@N0897-MAC ~ % ssh csd3

        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>
        <>                                                        <>
        <>                        !WARNING!                       <>
        <>                                                        <>
        <>                    RCS CSD3 Facility                   <>
        <>             Unauthorised Access Prohibited             <>
        <>    Use of this system constitutes acceptance of our    <>
        <>                     policies - see                     <>
        <> http://docs.hpc.cam.ac.uk/hpc/user-guide/policies.html <>
        <>                                                        <>
        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>


(ir-lawa1@login-icelake.hpc.cam.ac.uk) TOTP Verification Code: 021574
Last login: Mon Oct  7 12:34:27 2024 from 194.81.236.242
[ir-lawa1@login-q-1 ~]$ cd rds
[ir-lawa1@login-q-1 rds]$ ls
rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-1 rds]$ cd rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-1 rds-ukaea-ap002-mOlK9qn0PlQ]$ cd ir-lawa1
[ir-lawa1@login-q-1 ir-lawa1]$ ls
airflow_test  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-1 ir-lawa1]$ cd airflow_test
[ir-lawa1@login-q-1 airflow_test]$ source py_venv/bin/activate
-bash: py_venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ ls
airflow.cfg  airflow.db  logs
[ir-lawa1@login-q-1 airflow_test]$ vim airflow.cfg
[ir-lawa1@login-q-1 airflow_test]$ vim -n airflow.cfg
[ir-lawa1@login-q-1 airflow_test]$ vim -n airflow.cfg
[ir-lawa1@login-q-1 airflow_test]$ airflow db init
-bash: airflow: command not found
[ir-lawa1@login-q-1 airflow_test]$ source py_venv/bin/activate
-bash: py_venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ ls
airflow.cfg  airflow.db  logs
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python3.12
error: unexpected argument '--python3.12' found

  tip: a similar argument exists: '--python'

Usage: uv venv --python <PYTHON> [PATH]

For more information, try '--help'.
[ir-lawa1@login-q-1 airflow_test]$ uv venv --pytho
error: unexpected argument '--pytho' found

  tip: a similar argument exists: '--python'

Usage: uv venv --python <PYTHON> [PATH]

For more information, try '--help'.
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python
error: a value is required for '--python <PYTHON>' but none was supplied

For more information, try '--help'.
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
(airflow_test) [ir-lawa1@login-q-1 airflow_test]$ ls
airflow.cfg  airflow.db  logs
(airflow_test) [ir-lawa1@login-q-1 airflow_test]$ pip install apache-airflow
-bash: pip: command not found
(airflow_test) [ir-lawa1@login-q-1 airflow_test]$ uv pip install apache-airflow
Resolved 140 packages in 2.84s
Prepared 1 package in 110ms
░░░░░░░░░░░░░░░░░░░░ [0/140] Installing wheels...                                                                                                                                                                     warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: apache_airflow-2.10.2-py3-none-any.http.whl (apache-airflow==2.10.2)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/-7EITpbHt6nsxWxoLMHYR/airflow/migrations/versions/0093_2_2_0_taskinstance_keyed_to_dagrun.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/airflow/migrations/versions/0093_2_2_0_taskinstance_keyed_to_dagrun.py
  Caused by: Quota exceeded (os error 122)
(airflow_test) [ir-lawa1@login-q-1 airflow_test]$ airflow
-bash: airflow: command not found
(airflow_test) [ir-lawa1@login-q-1 airflow_test]$ ls /home/ir-lawa1/.cache/uv/archive-v0/-7EITpbHt6nsxWxoLMHYR/airflow/migrations/versions/0
ls: cannot access '/home/ir-lawa1/.cache/uv/archive-v0/-7EITpbHt6nsxWxoLMHYR/airflow/migrations/versions/0': No such file or directory
(airflow_test) [ir-lawa1@login-q-1 airflow_test]$ sudo ls /home/ir-lawa1/.cache/uv/archive-v0/-7EITpbHt6nsxWxoLMHYR/airflow/migrations/versions/0

We trust you have received the usual lecture from the local System
Administrator. It usually boils down to these three things:

    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.

[sudo] password for ir-lawa1: 
Sorry, try again.
[sudo] password for ir-lawa1: 
Sorry, try again.
[sudo] password for ir-lawa1: 
sudo: 2 incorrect password attempts
(airflow_test) [ir-lawa1@login-q-1 airflow_test]$ uv pip install apache-airflow
⠙ opentelemetry-exporter-otlp-proto-common==1.27.0                                                                                                                                                                    error: Failed to read metadata from installed package `googleapis-common-protos==1.65.0`
  Caused by: Failed to parse `METADATA` file at: .venv/lib/python3.12/site-packages/googleapis_common_protos-1.65.0.dist-info/METADATA
  Caused by: Metadata field Name not found
(airflow_test) [ir-lawa1@login-q-1 airflow_test]$ deactivate
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ├─▶ failed to write to file `/rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/.gitignore`
  ╰─▶ Quota exceeded (os error 122)
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
-bash: .venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
-bash: .venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
-bash: .venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ exit
logout
Connection to login-icelake.hpc.cam.ac.uk closed.
ds2718@N0897-MAC ~ % ssh csd3

        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>
        <>                                                        <>
        <>                        !WARNING!                       <>
        <>                                                        <>
        <>                    RCS CSD3 Facility                   <>
        <>             Unauthorised Access Prohibited             <>
        <>    Use of this system constitutes acceptance of our    <>
        <>                     policies - see                     <>
        <> http://docs.hpc.cam.ac.uk/hpc/user-guide/policies.html <>
        <>                                                        <>
        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>


(ir-lawa1@login-icelake.hpc.cam.ac.uk) TOTP Verification Code: 199213
Last login: Tue Oct  8 08:13:05 2024 from 194.81.236.242
[ir-lawa1@login-q-1 ~]$ ls
rds  slurm_submit.peta4-cclake  slurm_submit.peta4-icelake  slurm_submit.wilkes3
[ir-lawa1@login-q-1 ~]$ cd rds
[ir-lawa1@login-q-1 rds]$ ls
rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-1 rds]$ cd rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-1 rds-ukaea-ap002-mOlK9qn0PlQ]$ cd ir-lawal
-bash: cd: ir-lawal: No such file or directory
[ir-lawa1@login-q-1 rds-ukaea-ap002-mOlK9qn0PlQ]$ cd ir-lawa1
[ir-lawa1@login-q-1 ir-lawa1]$ ls
airflow_test  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-1 ir-lawa1]$ cd airflow_test
[ir-lawa1@login-q-1 airflow_test]$ ls
airflow.cfg  airflow.db  logs
[ir-lawa1@login-q-1 airflow_test]$ cd logs
[ir-lawa1@login-q-1 logs]$ ls
scheduler
[ir-lawa1@login-q-1 logs]$ cd scheduler
[ir-lawa1@login-q-1 scheduler]$ ls
2024-10-07  latest
[ir-lawa1@login-q-1 scheduler]$ cd lates
-bash: cd: lates: No such file or directory
[ir-lawa1@login-q-1 scheduler]$ cd latest
[ir-lawa1@login-q-1 latest]$ ls
[ir-lawa1@login-q-1 latest]$ cd ../../
[ir-lawa1@login-q-1 logs]$ cd ..
[ir-lawa1@login-q-1 airflow_test]$ ls
airflow.cfg  airflow.db  logs
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
-bash: .venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
-bash: .venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ ls
airflow.cfg  airflow.db  logs
[ir-lawa1@login-q-1 airflow_test]$ vim airflow.db
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
-bash: .venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
-bash: .venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ airflow
-bash: airflow: command not found
[ir-lawa1@login-q-1 airflow_test]$ pip install apache-airflow
-bash: pip: command not found
[ir-lawa1@login-q-1 airflow_test]$ deactivate
-bash: deactivate: command not found
[ir-lawa1@login-q-1 airflow_test]$ activate
-bash: activate: command not found
[ir-lawa1@login-q-1 airflow_test]$ pip install apache-airflow
-bash: pip: command not found
[ir-lawa1@login-q-1 airflow_test]$ python3
Python 3.6.8 (default, Apr 24 2024, 21:55:04) 
[GCC 8.5.0 20210514 (Red Hat 8.5.0-22)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> pip install
  File "<stdin>", line 1
    pip install
              ^
SyntaxError: invalid syntax
>>> pip install apache-airflow
  File "<stdin>", line 1
    pip install apache-airflow
              ^
SyntaxError: invalid syntax
>>> pip3 install apache-airflow
  File "<stdin>", line 1
    pip3 install apache-airflow
               ^
SyntaxError: invalid syntax
>>> q
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'q' is not defined
>>> exit
Use exit() or Ctrl-D (i.e. EOF) to exit
>>> exit()
[ir-lawa1@login-q-1 airflow_test]$ source .venv/bin/activate
-bash: .venv/bin/activate: No such file or directory
[ir-lawa1@login-q-1 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ uv venv
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ uv
An extremely fast Python package manager.

Usage: uv [OPTIONS] <COMMAND>

Commands:
  run      Run a command or script
  init     Create a new project
  add      Add dependencies to the project
  remove   Remove dependencies from the project
  sync     Update the project's environment
  lock     Update the project's lockfile
  export   Export the project's lockfile to an alternate format
  tree     Display the project's dependency tree
  tool     Run and install commands provided by Python packages
  python   Manage Python versions and installations
  pip      Manage Python packages with a pip-compatible interface
  venv     Create a virtual environment
  build    Build Python packages into source distributions and wheels
  publish  Upload distributions to an index
  cache    Manage uv's cache
  self     Manage the uv executable
  version  Display uv's version
  help     Display documentation for a command

Cache options:
  -n, --no-cache               Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation [env: UV_NO_CACHE=]
      --cache-dir <CACHE_DIR>  Path to the cache directory [env: UV_CACHE_DIR=]

Python options:
      --python-preference <PYTHON_PREFERENCE>  Whether to prefer uv-managed or system Python installations [env: UV_PYTHON_PREFERENCE=] [possible values: only-managed, managed, system, only-system]
      --no-python-downloads                    Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]

Global options:
  -q, --quiet                      Do not print any output
  -v, --verbose...                 Use verbose output
      --color <COLOR_CHOICE>       Control colors in output [default: auto] [possible values: auto, always, never]
      --native-tls                 Whether to load TLS certificates from the platform's native certificate store [env: UV_NATIVE_TLS=]
      --offline                    Disable network access
      --no-progress                Hide all progress outputs
      --directory <DIRECTORY>      Change to the given directory prior to running the command
      --project <PROJECT>          Run the command within the given project directory
      --config-file <CONFIG_FILE>  The path to a `uv.toml` file to use for configuration [env: UV_CONFIG_FILE=]
      --no-config                  Avoid discovering configuration files (`pyproject.toml`, `uv.toml`) [env: UV_NO_CONFIG=]
  -h, --help                       Display the concise help for this command
  -V, --version                    Display the uv version

Use `uv help` for more details.
[ir-lawa1@login-q-1 airflow_test]$ uv --no-cache venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ uv -n venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ uv
An extremely fast Python package manager.

Usage: uv [OPTIONS] <COMMAND>

Commands:
  run      Run a command or script
  init     Create a new project
  add      Add dependencies to the project
  remove   Remove dependencies from the project
  sync     Update the project's environment
  lock     Update the project's lockfile
  export   Export the project's lockfile to an alternate format
  tree     Display the project's dependency tree
  tool     Run and install commands provided by Python packages
  python   Manage Python versions and installations
  pip      Manage Python packages with a pip-compatible interface
  venv     Create a virtual environment
  build    Build Python packages into source distributions and wheels
  publish  Upload distributions to an index
  cache    Manage uv's cache
  self     Manage the uv executable
  version  Display uv's version
  help     Display documentation for a command

Cache options:
  -n, --no-cache               Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation [env: UV_NO_CACHE=]
      --cache-dir <CACHE_DIR>  Path to the cache directory [env: UV_CACHE_DIR=]

Python options:
      --python-preference <PYTHON_PREFERENCE>  Whether to prefer uv-managed or system Python installations [env: UV_PYTHON_PREFERENCE=] [possible values: only-managed, managed, system, only-system]
      --no-python-downloads                    Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]

Global options:
  -q, --quiet                      Do not print any output
  -v, --verbose...                 Use verbose output
      --color <COLOR_CHOICE>       Control colors in output [default: auto] [possible values: auto, always, never]
      --native-tls                 Whether to load TLS certificates from the platform's native certificate store [env: UV_NATIVE_TLS=]
      --offline                    Disable network access
      --no-progress                Hide all progress outputs
      --directory <DIRECTORY>      Change to the given directory prior to running the command
      --project <PROJECT>          Run the command within the given project directory
      --config-file <CONFIG_FILE>  The path to a `uv.toml` file to use for configuration [env: UV_CONFIG_FILE=]
      --no-config                  Avoid discovering configuration files (`pyproject.toml`, `uv.toml`) [env: UV_NO_CONFIG=]
  -h, --help                       Display the concise help for this command
  -V, --version                    Display the uv version

Use `uv help` for more details.
[ir-lawa1@login-q-1 airflow_test]$ uv .venv --python 3.12
error: unrecognized subcommand '.venv'

  tip: some similar subcommands exist: 'v', 'venv'

Usage: uv [OPTIONS] <COMMAND>

For more information, try '--help'.
[ir-lawa1@login-q-1 airflow_test]$ uv v --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ╰─▶ The directory `.venv` exists, but it's not a virtual environment
[ir-lawa1@login-q-1 airflow_test]$ uvRead from remote host login-icelake.hpc.cam.ac.uk: No route to host
Connection to login-icelake.hpc.cam.ac.uk closed.
client_loop: send disconnect: Broken pipe
ds2718@N0897-MAC ~ % ssh csd3

        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>
        <>                                                        <>
        <>                        !WARNING!                       <>
        <>                                                        <>
        <>                    RCS CSD3 Facility                   <>
        <>             Unauthorised Access Prohibited             <>
        <>    Use of this system constitutes acceptance of our    <>
        <>                     policies - see                     <>
        <> http://docs.hpc.cam.ac.uk/hpc/user-guide/policies.html <>
        <>                                                        <>
        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>


(ir-lawa1@login-icelake.hpc.cam.ac.uk) TOTP Verification Code: 753331
Last login: Tue Oct  8 05:05:50 2024 from shef-17-b2-v4wan-169236-cust29.vm3.cable.virginm.net
[ir-lawa1@login-q-2 ~]$ cd rds
[ir-lawa1@login-q-2 rds]$ ls
rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-2 rds]$ cd rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-2 rds-ukaea-ap002-mOlK9qn0PlQ]$ cd ir-lawa1
[ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow_test  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-2 ir-lawa1]$ cd airflow_test
[ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs
[ir-lawa1@login-q-2 airflow_test]$ uv venv py_venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: py_venv
Activate with: source py_venv/bin/activate
[ir-lawa1@login-q-2 airflow_test]$ source py_venv/bin/activate
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ pip install apache-airflow
-bash: pip: command not found
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ uv pip install apache-airflow
Resolved 140 packages in 2.09s
░░░░░░░░░░░░░░░░░░░░ [0/140] Installing wheels...                                                                                                                                                                     warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: aiohttp-3.10.9-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.http.whl (aiohttp==3.10.9)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/fMOKbKGN19zISvDbB_ARu/aiohttp/.hash/_cparser.pxd.hash to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/site-packages/aiohttp/.hash/_cparser.pxd.hash
  Caused by: Quota exceeded (os error 122)
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ uv pip install numpy
Resolved 1 package in 358ms
Prepared 1 package in 3.83s
░░░░░░░░░░░░░░░░░░░░ [0/1] Installing wheels...                                                                                                                                                                       warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: numpy-2.1.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (numpy==2.1.2)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/xSegOEhCKa-4K6-z4rh4g/numpy/lib/_index_tricks_impl.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/site-packages/numpy/lib/_index_tricks_impl.py
  Caused by: Quota exceeded (os error 122)
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ uv pip install --no-cachenumpy
error: unexpected argument '--no-cachenumpy' found

  tip: a similar argument exists: '--no-cache'

Usage: uv pip install --no-cache <PACKAGE|--requirement <REQUIREMENT>|--editable <EDITABLE>>

For more information, try '--help'.
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ uv pip install --no-cache numpy
Resolved 1 package in 151ms
Prepared 1 package in 342ms
error: Failed to install: numpy-2.1.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (numpy==2.1.2)
  Caused by: failed to copy file from /tmp/.tmpxzmXvz/archive-v0/FzBRgxmSfSGRwIBESJPu8/numpy/exceptions.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/site-packages/numpy/exceptions.py
  Caused by: Quota exceeded (os error 122)
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/site-packages/
aiohappyeyeballs                                        _distutils_hack                                mako                                                       rfc3339_validator.py
aiohappyeyeballs-2.4.3.dist-info                        distutils-precedence.pth                       Mako-1.3.5.dist-info                                       rich
aiohttp                                                 dns                                            markdown_it                                                rich-13.9.2.dist-info
aiohttp-3.10.9.dist-info                                docutils                                       markupsafe                                                 rich_argparse
aiohttp.libs                                            flask                                          MarkupSafe-3.0.0.dist-info                                 rich_argparse-1.5.2.dist-info
aiosignal                                               Flask-2.2.5.dist-info                          marshmallow                                                rpds
aiosignal-1.3.1.dist-info                               flask_appbuilder                               marshmallow-3.22.0.dist-info                               rpds_py-0.20.0.dist-info
airflow                                                 flask_babel                                    marshmallow_oneofschema                                    setproctitle
alembic                                                 Flask_Babel-2.0.0.dist-info                    marshmallow_oneofschema-3.1.1.dist-info                    setproctitle-1.3.3.dist-info
anyio                                                   flask_caching                                  mdit_py_plugins                                            setproctitle.libs
anyio-4.6.0.dist-info                                   Flask_Caching-2.3.0.dist-info                  mdurl                                                      setuptools
apache_airflow_providers_common_compat-1.2.0.dist-info  flask_jwt_extended                             mdurl-0.1.2.dist-info                                      setuptools-75.1.0.dist-info
apache_airflow_providers_common_io-1.4.1.dist-info      Flask_JWT_Extended-4.6.0.dist-info             methodtools-0.4.7.dist-info                                six-1.16.0.dist-info
apache_airflow_providers_common_sql-1.17.1.dist-info    flask_limiter                                  methodtools.py                                             six.py
apache_airflow_providers_fab-1.4.0.dist-info            Flask_Limiter-3.8.0.dist-info                  more_itertools                                             slugify
apache_airflow_providers_ftp-3.11.1.dist-info           flask_login                                    more_itertools-10.5.0.dist-info                            sniffio
apache_airflow_providers_http-4.13.1.dist-info          Flask_Login-0.6.3.dist-info                    multidict                                                  sniffio-1.3.1.dist-info
apache_airflow_providers_imap-3.7.0.dist-info           flask_session                                  multidict-6.1.0.dist-info                                  sqlparse
apache_airflow_providers_smtp-1.8.0.dist-info           flask_session-0.5.0.dist-info                  multidict.libs                                             sqlparse-0.5.1.dist-info
apache_airflow_providers_sqlite-3.9.0.dist-info         flask_sqlalchemy                               numpy                                                      tabulate
apispec                                                 Flask_SQLAlchemy-2.5.1.dist-info               opentelemetry                                              tabulate-0.9.0.dist-info
asgiref                                                 flask_wtf                                      opentelemetry_exporter_otlp-1.27.0.dist-info               tenacity
asgiref-3.8.1.dist-info                                 flask_wtf-1.2.1.dist-info                      opentelemetry_exporter_otlp_proto_common-1.27.0.dist-info  tenacity-9.0.0.dist-info
attr                                                    frozenlist                                     opentelemetry_exporter_otlp_proto_grpc-1.27.0.dist-info    termcolor
attrs                                                   frozenlist-1.4.1.dist-info                     opentelemetry_exporter_otlp_proto_http-1.27.0.dist-info    termcolor-2.5.0.dist-info
attrs-24.2.0.dist-info                                  frozenlist.libs                                opentelemetry_sdk-1.27.0.dist-info                         text_unidecode
babel                                                   fsspec                                         ordered_set                                                text_unidecode-1.3.dist-info
blinker                                                 fsspec-2024.9.0.dist-info                      ordered_set-4.1.0.dist-info                                time_machine
blinker-1.8.2.dist-info                                 google                                         packaging                                                  time_machine-2.15.0.dist-info
cachelib                                                google_re2-1.1.20240702.dist-info              packaging-24.1.dist-info                                   _time_machine.cpython-312-x86_64-linux-gnu.so
cachelib-0.9.0.dist-info                                greenlet                                       pathspec                                                   time_machine.libs
certifi                                                 greenlet-3.1.1.data                            pathspec-0.12.1.dist-info                                  typing_extensions-4.12.2.dist-info
certifi-2024.8.30.dist-info                             grpc                                           pendulum                                                   typing_extensions.py
cffi                                                    grpcio-1.66.2.dist-info                        pendulum-3.0.0.dist-info                                   tzdata
cffi-1.17.1.dist-info                                   gunicorn                                       pkg_resources                                              uc_micro
_cffi_backend.cpython-312-x86_64-linux-gnu.so           gunicorn-23.0.0.dist-info                      prison                                                     uc_micro_py-1.0.3.dist-info
cffi.libs                                               h11                                            prison-0.2.1.dist-info                                     unicodecsv
charset_normalizer                                      h11-0.14.0.dist-info                           protobuf-4.25.5.dist-info                                  unicodecsv-0.14.1.dist-info
charset_normalizer-3.3.2.dist-info                      httpcore                                       psutil                                                     upath
charset_normalizer.libs                                 httpcore-1.0.6.dist-info                       psutil-6.0.0.dist-info                                     urllib3
click                                                   httpx                                          psutil.libs                                                urllib3-2.2.3.dist-info
clickclick                                              httpx-0.27.2.dist-info                         pygments                                                   _virtualenv.pth
clickclick-20.10.2.dist-info                            idna                                           pygments-2.18.0.dist-info                                  _virtualenv.py
colorama                                                idna-3.10.dist-info                            PyJWT-2.9.0.dist-info                                      werkzeug
colorama-0.4.6.dist-info                                importlib_resources                            python_daemon-3.0.1.dist-info                              wirerope
colorlog                                                importlib_resources-6.4.5.dist-info            python_slugify-8.0.4.dist-info                             wirerope-0.4.7.dist-info
colorlog-6.8.2.dist-info                                jmespath                                       pytz                                                       wrapt
configupdater                                           jmespath-1.0.1.dist-info                       PyYAML-6.0.2.dist-info                                     wrapt-1.16.0.dist-info
ConfigUpdater-3.2.dist-info                             jsonschema                                     PyYAML.libs                                                wrapt.libs
connexion                                               jsonschema-4.23.0.dist-info                    re2                                                        wtforms
connexion-2.14.2.dist-info                              jsonschema_specifications                      referencing                                                wtforms-3.1.2.dist-info
cron_descriptor                                         jsonschema_specifications-2023.12.1.dist-info  referencing-0.35.1.dist-info                               _yaml
cron_descriptor-1.4.5.dist-info                         jwt                                            requests                                                   yaml
croniter-3.0.3.dist-info                                linkify_it                                     requests-2.32.3.dist-info                                  yarl
daemon                                                  linkify_it_py-2.0.3.dist-info                  requests_toolbelt                                          yarl-1.13.1.dist-info
dill                                                    lockfile                                       requests_toolbelt-1.0.0.dist-info                          zipp
dill-0.3.9.dist-info                                    lockfile-0.12.2.dist-info                      rfc3339_validator-0.1.4.dist-info                          zipp-3.20.2.dist-info
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ airflow
-bash: airflow: command not found
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/
ls: cannot access '/rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/': No such file or directory
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/venv/lib/python3.12/site-packages/
ls: cannot access '/rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/venv/lib/python3.12/site-packages/': No such file or directory
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/site-packages/
aiohappyeyeballs                                        _distutils_hack                                mako                                                       rfc3339_validator.py
aiohappyeyeballs-2.4.3.dist-info                        distutils-precedence.pth                       Mako-1.3.5.dist-info                                       rich
aiohttp                                                 dns                                            markdown_it                                                rich-13.9.2.dist-info
aiohttp-3.10.9.dist-info                                docutils                                       markupsafe                                                 rich_argparse
aiohttp.libs                                            flask                                          MarkupSafe-3.0.0.dist-info                                 rich_argparse-1.5.2.dist-info
aiosignal                                               Flask-2.2.5.dist-info                          marshmallow                                                rpds
aiosignal-1.3.1.dist-info                               flask_appbuilder                               marshmallow-3.22.0.dist-info                               rpds_py-0.20.0.dist-info
airflow                                                 flask_babel                                    marshmallow_oneofschema                                    setproctitle
alembic                                                 Flask_Babel-2.0.0.dist-info                    marshmallow_oneofschema-3.1.1.dist-info                    setproctitle-1.3.3.dist-info
anyio                                                   flask_caching                                  mdit_py_plugins                                            setproctitle.libs
anyio-4.6.0.dist-info                                   Flask_Caching-2.3.0.dist-info                  mdurl                                                      setuptools
apache_airflow_providers_common_compat-1.2.0.dist-info  flask_jwt_extended                             mdurl-0.1.2.dist-info                                      setuptools-75.1.0.dist-info
apache_airflow_providers_common_io-1.4.1.dist-info      Flask_JWT_Extended-4.6.0.dist-info             methodtools-0.4.7.dist-info                                six-1.16.0.dist-info
apache_airflow_providers_common_sql-1.17.1.dist-info    flask_limiter                                  methodtools.py                                             six.py
apache_airflow_providers_fab-1.4.0.dist-info            Flask_Limiter-3.8.0.dist-info                  more_itertools                                             slugify
apache_airflow_providers_ftp-3.11.1.dist-info           flask_login                                    more_itertools-10.5.0.dist-info                            sniffio
apache_airflow_providers_http-4.13.1.dist-info          Flask_Login-0.6.3.dist-info                    multidict                                                  sniffio-1.3.1.dist-info
apache_airflow_providers_imap-3.7.0.dist-info           flask_session                                  multidict-6.1.0.dist-info                                  sqlparse
apache_airflow_providers_smtp-1.8.0.dist-info           flask_session-0.5.0.dist-info                  multidict.libs                                             sqlparse-0.5.1.dist-info
apache_airflow_providers_sqlite-3.9.0.dist-info         flask_sqlalchemy                               numpy                                                      tabulate
apispec                                                 Flask_SQLAlchemy-2.5.1.dist-info               opentelemetry                                              tabulate-0.9.0.dist-info
asgiref                                                 flask_wtf                                      opentelemetry_exporter_otlp-1.27.0.dist-info               tenacity
asgiref-3.8.1.dist-info                                 flask_wtf-1.2.1.dist-info                      opentelemetry_exporter_otlp_proto_common-1.27.0.dist-info  tenacity-9.0.0.dist-info
attr                                                    frozenlist                                     opentelemetry_exporter_otlp_proto_grpc-1.27.0.dist-info    termcolor
attrs                                                   frozenlist-1.4.1.dist-info                     opentelemetry_exporter_otlp_proto_http-1.27.0.dist-info    termcolor-2.5.0.dist-info
attrs-24.2.0.dist-info                                  frozenlist.libs                                opentelemetry_sdk-1.27.0.dist-info                         text_unidecode
babel                                                   fsspec                                         ordered_set                                                text_unidecode-1.3.dist-info
blinker                                                 fsspec-2024.9.0.dist-info                      ordered_set-4.1.0.dist-info                                time_machine
blinker-1.8.2.dist-info                                 google                                         packaging                                                  time_machine-2.15.0.dist-info
cachelib                                                google_re2-1.1.20240702.dist-info              packaging-24.1.dist-info                                   _time_machine.cpython-312-x86_64-linux-gnu.so
cachelib-0.9.0.dist-info                                greenlet                                       pathspec                                                   time_machine.libs
certifi                                                 greenlet-3.1.1.data                            pathspec-0.12.1.dist-info                                  typing_extensions-4.12.2.dist-info
certifi-2024.8.30.dist-info                             grpc                                           pendulum                                                   typing_extensions.py
cffi                                                    grpcio-1.66.2.dist-info                        pendulum-3.0.0.dist-info                                   tzdata
cffi-1.17.1.dist-info                                   gunicorn                                       pkg_resources                                              uc_micro
_cffi_backend.cpython-312-x86_64-linux-gnu.so           gunicorn-23.0.0.dist-info                      prison                                                     uc_micro_py-1.0.3.dist-info
cffi.libs                                               h11                                            prison-0.2.1.dist-info                                     unicodecsv
charset_normalizer                                      h11-0.14.0.dist-info                           protobuf-4.25.5.dist-info                                  unicodecsv-0.14.1.dist-info
charset_normalizer-3.3.2.dist-info                      httpcore                                       psutil                                                     upath
charset_normalizer.libs                                 httpcore-1.0.6.dist-info                       psutil-6.0.0.dist-info                                     urllib3
click                                                   httpx                                          psutil.libs                                                urllib3-2.2.3.dist-info
clickclick                                              httpx-0.27.2.dist-info                         pygments                                                   _virtualenv.pth
clickclick-20.10.2.dist-info                            idna                                           pygments-2.18.0.dist-info                                  _virtualenv.py
colorama                                                idna-3.10.dist-info                            PyJWT-2.9.0.dist-info                                      werkzeug
colorama-0.4.6.dist-info                                importlib_resources                            python_daemon-3.0.1.dist-info                              wirerope
colorlog                                                importlib_resources-6.4.5.dist-info            python_slugify-8.0.4.dist-info                             wirerope-0.4.7.dist-info
colorlog-6.8.2.dist-info                                jmespath                                       pytz                                                       wrapt
configupdater                                           jmespath-1.0.1.dist-info                       PyYAML-6.0.2.dist-info                                     wrapt-1.16.0.dist-info
ConfigUpdater-3.2.dist-info                             jsonschema                                     PyYAML.libs                                                wrapt.libs
connexion                                               jsonschema-4.23.0.dist-info                    re2                                                        wtforms
connexion-2.14.2.dist-info                              jsonschema_specifications                      referencing                                                wtforms-3.1.2.dist-info
cron_descriptor                                         jsonschema_specifications-2023.12.1.dist-info  referencing-0.35.1.dist-info                               _yaml
cron_descriptor-1.4.5.dist-info                         jwt                                            requests                                                   yaml
croniter-3.0.3.dist-info                                linkify_it                                     requests-2.32.3.dist-info                                  yarl
daemon                                                  linkify_it_py-2.0.3.dist-info                  requests_toolbelt                                          yarl-1.13.1.dist-info
dill                                                    lockfile                                       requests_toolbelt-1.0.0.dist-info                          zipp
dill-0.3.9.dist-info                                    lockfile-0.12.2.dist-info                      rfc3339_validator-0.1.4.dist-info                          zipp-3.20.2.dist-info
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12
site-packages
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib
python3.12
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv
bin  CACHEDIR.TAG  lib  lib64  pyvenv.cfg
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test
airflow.cfg  airflow.db  logs  py_venv
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs  py_venv
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ airflow
-bash: airflow: command not found
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ apache-airflow
-bash: apache-airflow: command not found
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ rm -rf /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test
airflow.cfg  airflow.db  logs
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ uv venv py_venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: py_venv
Activate with: source py_venv/bin/activate
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ source py_venv/bin/activate
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv
bin  CACHEDIR.TAG  lib  lib64  pyvenv.cfg
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ uv pip install apache-airflow
Resolved 140 packages in 430ms
░░░░░░░░░░░░░░░░░░░░ [0/140] Installing wheels...                                                                                                                                                                     warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: aiohttp-3.10.9-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.http.whl (aiohttp==3.10.9)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/fMOKbKGN19zISvDbB_ARu/aiohttp/_helpers.pyi to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/site-packages/aiohttp/_helpers.pyi
  Caused by: Quota exceeded (os error 122)
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/
-bash: /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/: Is a directory
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/
site-packages
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv/lib/python3.12/site-packages/
aiohappyeyeballs                                        distutils-precedence.pth                       lockfile                                                   requests_toolbelt-1.0.0.dist-info
aiohappyeyeballs-2.4.3.dist-info                        dns                                            lockfile-0.12.2.dist-info                                  rfc3339_validator-0.1.4.dist-info
aiohttp                                                 docutils                                       mako                                                       rfc3339_validator.py
aiohttp-3.10.9.dist-info                                email_validator                                Mako-1.3.5.dist-info                                       rich
aiohttp.libs                                            email_validator-2.2.0.dist-info                markdown_it                                                rich-13.9.2.dist-info
aiosignal                                               flask                                          markdown_it_py-3.0.0.dist-info                             rich_argparse
aiosignal-1.3.1.dist-info                               Flask-2.2.5.dist-info                          markupsafe                                                 rich_argparse-1.5.2.dist-info
airflow                                                 flask_appbuilder                               MarkupSafe-3.0.0.dist-info                                 rpds
alembic                                                 flask_babel                                    marshmallow                                                rpds_py-0.20.0.dist-info
alembic-1.13.3.dist-info                                Flask_Babel-2.0.0.dist-info                    marshmallow-3.22.0.dist-info                               setproctitle
anyio                                                   flask_caching                                  marshmallow_oneofschema                                    setproctitle-1.3.3.dist-info
anyio-4.6.0.dist-info                                   Flask_Caching-2.3.0.dist-info                  marshmallow_oneofschema-3.1.1.dist-info                    setproctitle.libs
apache_airflow_providers_common_compat-1.2.0.dist-info  flask_jwt_extended                             marshmallow_sqlalchemy                                     setuptools
apache_airflow_providers_common_io-1.4.1.dist-info      Flask_JWT_Extended-4.6.0.dist-info             marshmallow_sqlalchemy-0.28.2.dist-info                    setuptools-75.1.0.dist-info
apache_airflow_providers_common_sql-1.17.1.dist-info    flask_limiter                                  mdit_py_plugins                                            six-1.16.0.dist-info
apache_airflow_providers_fab-1.4.0.dist-info            Flask_Limiter-3.8.0.dist-info                  mdit_py_plugins-0.4.2.dist-info                            six.py
apache_airflow_providers_ftp-3.11.1.dist-info           flask_login                                    mdurl                                                      slugify
apache_airflow_providers_http-4.13.1.dist-info          Flask_Login-0.6.3.dist-info                    mdurl-0.1.2.dist-info                                      sniffio
apache_airflow_providers_imap-3.7.0.dist-info           flask_session                                  methodtools-0.4.7.dist-info                                sniffio-1.3.1.dist-info
apache_airflow_providers_smtp-1.8.0.dist-info           flask_session-0.5.0.dist-info                  methodtools.py                                             sqlalchemy
apache_airflow_providers_sqlite-3.9.0.dist-info         flask_sqlalchemy                               more_itertools                                             SQLAlchemy-1.4.54.dist-info
apispec                                                 Flask_SQLAlchemy-2.5.1.dist-info               more_itertools-10.5.0.dist-info                            sqlalchemy_jsonfield
apispec-6.6.1.dist-info                                 flask_wtf                                      multidict                                                  SQLAlchemy_JSONField-1.0.2.dist-info
argcomplete                                             flask_wtf-1.2.1.dist-info                      multidict-6.1.0.dist-info                                  sqlalchemy_utils
argcomplete-3.5.1.dist-info                             frozenlist                                     multidict.libs                                             SQLAlchemy_Utils-0.41.2.dist-info
asgiref                                                 frozenlist-1.4.1.dist-info                     nvd3                                                       sqlparse
asgiref-3.8.1.dist-info                                 frozenlist.libs                                opentelemetry                                              sqlparse-0.5.1.dist-info
attr                                                    fsspec                                         opentelemetry_api-1.27.0.dist-info                         tabulate
attrs                                                   google                                         opentelemetry_exporter_otlp-1.27.0.dist-info               tabulate-0.9.0.dist-info
attrs-24.2.0.dist-info                                  google_re2-1.1.20240702.dist-info              opentelemetry_exporter_otlp_proto_common-1.27.0.dist-info  tenacity
babel                                                   greenlet                                       opentelemetry_exporter_otlp_proto_grpc-1.27.0.dist-info    tenacity-9.0.0.dist-info
blinker                                                 greenlet-3.1.1.data                            opentelemetry_exporter_otlp_proto_http-1.27.0.dist-info    termcolor
blinker-1.8.2.dist-info                                 grpc                                           opentelemetry_proto-1.27.0.dist-info                       termcolor-2.5.0.dist-info
cachelib                                                grpcio-1.66.2.dist-info                        opentelemetry_sdk-1.27.0.dist-info                         text_unidecode
cachelib-0.9.0.dist-info                                gunicorn                                       ordered_set                                                text_unidecode-1.3.dist-info
certifi                                                 gunicorn-23.0.0.dist-info                      ordered_set-4.1.0.dist-info                                time_machine
certifi-2024.8.30.dist-info                             h11                                            packaging                                                  time_machine-2.15.0.dist-info
cffi                                                    h11-0.14.0.dist-info                           packaging-24.1.dist-info                                   _time_machine.cpython-312-x86_64-linux-gnu.so
cffi-1.17.1.dist-info                                   httpcore                                       pathspec                                                   time_machine.libs
_cffi_backend.cpython-312-x86_64-linux-gnu.so           httpcore-1.0.6.dist-info                       pathspec-0.12.1.dist-info                                  typing_extensions-4.12.2.dist-info
cffi.libs                                               httpx                                          pendulum                                                   typing_extensions.py
charset_normalizer                                      httpx-0.27.2.dist-info                         pendulum-3.0.0.dist-info                                   tzdata
charset_normalizer-3.3.2.dist-info                      idna                                           pkg_resources                                              uc_micro
charset_normalizer.libs                                 idna-3.10.dist-info                            pluggy                                                     uc_micro_py-1.0.3.dist-info
click                                                   importlib_metadata                             pluggy-1.5.0.dist-info                                     unicodecsv
click-8.1.7.dist-info                                   importlib_metadata-8.4.0.dist-info             prison                                                     unicodecsv-0.14.1.dist-info
clickclick                                              importlib_resources                            prison-0.2.1.dist-info                                     universal_pathlib-0.2.5.dist-info
clickclick-20.10.2.dist-info                            importlib_resources-6.4.5.dist-info            protobuf-4.25.5.dist-info                                  upath
colorama                                                inflection                                     psutil                                                     urllib3
colorama-0.4.6.dist-info                                inflection-0.5.1.dist-info                     psutil-6.0.0.dist-info                                     urllib3-2.2.3.dist-info
colorlog                                                inflection.py                                  psutil.libs                                                _virtualenv.pth
colorlog-6.8.2.dist-info                                itsdangerous                                   pycparser                                                  _virtualenv.py
configupdater                                           itsdangerous-2.2.0.dist-info                   pycparser-2.22.dist-info                                   werkzeug
ConfigUpdater-3.2.dist-info                             jinja2                                         pygments                                                   wirerope
connexion                                               jinja2-3.1.4.dist-info                         pygments-2.18.0.dist-info                                  wirerope-0.4.7.dist-info
connexion-2.14.2.dist-info                              jmespath                                       PyJWT-2.9.0.dist-info                                      wrapt
cron_descriptor                                         jmespath-1.0.1.dist-info                       python_daemon-3.0.1.dist-info                              wrapt-1.16.0.dist-info
cron_descriptor-1.4.5.dist-info                         jsonschema                                     python_dateutil-2.9.0.post0.dist-info                      wrapt.libs
croniter                                                jsonschema-4.23.0.dist-info                    python_nvd3-0.16.0.dist-info                               wtforms
croniter-3.0.3.dist-info                                jsonschema_specifications                      python_slugify-8.0.4.dist-info                             wtforms-3.1.2.dist-info
cryptography                                            jsonschema_specifications-2023.12.1.dist-info  pytz                                                       _yaml
cryptography-43.0.1.dist-info                           jwt                                            PyYAML-6.0.2.dist-info                                     yaml
daemon                                                  lazy_object_proxy                              PyYAML.libs                                                yarl
dateutil                                                lazy_object_proxy-1.10.0.dist-info             re2                                                        yarl-1.13.1.dist-info
deprecated                                              lazy_object_proxy.libs                         referencing                                                zipp
Deprecated-1.2.14.dist-info                             limits                                         referencing-0.35.1.dist-info                               zipp-3.20.2.dist-info
dill                                                    limits-3.13.0.dist-info                        requests
dill-0.3.9.dist-info                                    linkify_it                                     requests-2.32.3.dist-info
_distutils_hack                                         linkify_it_py-2.0.3.dist-info                  requests_toolbelt
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ deacdls
-bash: deacdls: command not found
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ 






(py_venv) [ir-lawa1@login-q-2 airflow_test]$ 
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ 
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ 
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ 
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ 
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ 
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs  py_venv
(py_venv) [ir-lawa1@login-q-2 airflow_test]$ deactivate
[ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs  py_venv
[ir-lawa1@login-q-2 airflow_test]$ rm -rf /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv
[ir-lawa1@login-q-2 airflow_test]$ uv venv py_venv python 3.12
error: unexpected argument 'python' found

Usage: uv venv [OPTIONS] [PATH]

For more information, try '--help'.
[ir-lawa1@login-q-2 airflow_test]$ uv venv py_venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: py_venv
Activate with: source py_venv/bin/activate
[ir-lawa1@login-q-2 airflow_test]$ rm -rf /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv
[ir-lawa1@login-q-2 airflow_test]$ rm -rf /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/py_venv
[ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs
[ir-lawa1@login-q-2 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
[ir-lawa1@login-q-2 airflow_test]$ uv pip install apache-airflow
Resolved 140 packages in 2.66s
░░░░░░░░░░░░░░░░░░░░ [0/140] Installing wheels...                                                                                                                                                                   warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: aiohttp-3.10.9-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.http.whl (aiohttp==3.10.9)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/fMOKbKGN19zISvDbB_ARu/aiohttp/web_protocol.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/aiohttp/web_protocol.py
  Caused by: Quota exceeded (os error 122)
[ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/
aiohappyeyeballs                                        charset_normalizer.libs             google                                                   pygments
aiohappyeyeballs-2.4.3.dist-info                        click                               greenlet                                                 pygments-2.18.0.dist-info
aiohttp                                                 click-8.1.7.dist-info               greenlet-3.1.1.data                                      python_slugify-8.0.4.dist-info
aiohttp-3.10.9.dist-info                                clickclick                          grpc                                                     pytz
aiohttp.libs                                            clickclick-20.10.2.dist-info        grpcio-1.66.2.dist-info                                  PyYAML-6.0.2.dist-info
aiosignal                                               colorama                            gunicorn                                                 PyYAML.libs
aiosignal-1.3.1.dist-info                               colorama-0.4.6.dist-info            gunicorn-23.0.0.dist-info                                referencing
airflow                                                 colorlog                            h11                                                      referencing-0.35.1.dist-info
alembic                                                 colorlog-6.8.2.dist-info            h11-0.14.0.dist-info                                     requests
alembic-1.13.3.dist-info                                configupdater                       httpcore                                                 requests-2.32.3.dist-info
anyio                                                   ConfigUpdater-3.2.dist-info         httpcore-1.0.6.dist-info                                 requests_toolbelt
anyio-4.6.0.dist-info                                   connexion                           httpx                                                    requests_toolbelt-1.0.0.dist-info
apache_airflow_providers_common_compat-1.2.0.dist-info  connexion-2.14.2.dist-info          httpx-0.27.2.dist-info                                   rfc3339_validator-0.1.4.dist-info
apache_airflow_providers_common_io-1.4.1.dist-info      cron_descriptor                     idna                                                     rfc3339_validator.py
apache_airflow_providers_common_sql-1.17.1.dist-info    cron_descriptor-1.4.5.dist-info     idna-3.10.dist-info                                      rich
apache_airflow_providers_fab-1.4.0.dist-info            croniter                            importlib_metadata                                       rich-13.9.2.dist-info
apache_airflow_providers_ftp-3.11.1.dist-info           croniter-3.0.3.dist-info            importlib_metadata-8.4.0.dist-info                       rich_argparse
apache_airflow_providers_http-4.13.1.dist-info          cryptography                        importlib_resources                                      rich_argparse-1.5.2.dist-info
apache_airflow_providers_imap-3.7.0.dist-info           cryptography-43.0.1.dist-info       importlib_resources-6.4.5.dist-info                      rpds
apache_airflow_providers_smtp-1.8.0.dist-info           deprecated                          inflection                                               rpds_py-0.20.0.dist-info
apache_airflow_providers_sqlite-3.9.0.dist-info         Deprecated-1.2.14.dist-info         inflection-0.5.1.dist-info                               setproctitle
apispec                                                 dill                                inflection.py                                            setproctitle-1.3.3.dist-info
apispec-6.6.1.dist-info                                 dill-0.3.9.dist-info                itsdangerous                                             setproctitle.libs
argcomplete                                             _distutils_hack                     itsdangerous-2.2.0.dist-info                             setuptools
argcomplete-3.5.1.dist-info                             distutils-precedence.pth            jmespath                                                 setuptools-75.1.0.dist-info
asgiref                                                 docutils                            jmespath-1.0.1.dist-info                                 six-1.16.0.dist-info
asgiref-3.8.1.dist-info                                 email_validator                     jsonschema_specifications                                six.py
attr                                                    email_validator-2.2.0.dist-info     jsonschema_specifications-2023.12.1.dist-info            slugify
attrs                                                   flask                               linkify_it                                               sniffio
attrs-24.2.0.dist-info                                  Flask-2.2.5.dist-info               linkify_it_py-2.0.3.dist-info                            sniffio-1.3.1.dist-info
babel                                                   flask_appbuilder                    markupsafe                                               sqlalchemy
blinker                                                 flask_babel                         MarkupSafe-3.0.0.dist-info                               SQLAlchemy-1.4.54.dist-info
blinker-1.8.2.dist-info                                 Flask_Babel-2.0.0.dist-info         marshmallow_oneofschema                                  sqlalchemy_jsonfield
cachelib                                                flask_caching                       marshmallow_oneofschema-3.1.1.dist-info                  SQLAlchemy_JSONField-1.0.2.dist-info
cachelib-0.9.0.dist-info                                Flask_Caching-2.3.0.dist-info       mdit_py_plugins                                          sqlparse
certifi                                                 flask_jwt_extended                  mdit_py_plugins-0.4.2.dist-info                          sqlparse-0.5.1.dist-info
certifi-2024.8.30.dist-info                             Flask_JWT_Extended-4.6.0.dist-info  opentelemetry                                            _virtualenv.pth
cffi                                                    flask_limiter                       opentelemetry_exporter_otlp_proto_http-1.27.0.dist-info  _virtualenv.py
cffi-1.17.1.dist-info                                   Flask_Limiter-3.8.0.dist-info       ordered_set                                              _yaml
_cffi_backend.cpython-312-x86_64-linux-gnu.so           flask_login                         ordered_set-4.1.0.dist-info                              yaml
cffi.libs                                               Flask_Login-0.6.3.dist-info         pkg_resources
charset_normalizer                                      flask_sqlalchemy                    prison
charset_normalizer-3.3.2.dist-info                      Flask_SQLAlchemy-2.5.1.dist-info    prison-0.2.1.dist-info
[ir-lawa1@login-q-2 airflow_test]$ rm /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/
rm: cannot remove '/rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/': Is a directory
[ir-lawa1@login-q-2 airflow_test]$ rm -rf /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv
[ir-lawa1@login-q-2 airflow_test]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
[ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/
_virtualenv.pth  _virtualenv.py
[ir-lawa1@login-q-2 airflow_test]$ source .venv/bin/activate
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ pip install numpy
-bash: pip: command not found
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ uv pip install numpy
Resolved 1 package in 137ms
░░░░░░░░░░░░░░░░░░░░ [0/1] Installing wheels...                                                                                                                                                                     warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: numpy-2.1.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.http.whl (numpy==2.1.2)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/xSegOEhCKa-4K6-z4rh4g/numpy/_core/tests/test_simd_module.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/numpy/_core/tests/test_simd_module.py
  Caused by: Quota exceeded (os error 122)
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/
numpy  _virtualenv.pth  _virtualenv.py
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_test/.venv/lib/python3.12/site-packages/
numpy  _virtualenv.pth  _virtualenv.py
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls /home/ir-lawa1/.cache/uv/archive-v0/
05l47I5lf0gvrkNcbSB72  8vL6wmj8ICpgLz-_nONzQ  cx-K45_QykhTDR61ffj4D  gZ1xHJZ1XMQ5sMkQ_btYv  kuA2OZRaqF_qbxun-OdGN  oV9LZo9NtlG74lldVvdQ1  rBA5M8aES_FT6SrvSvPJe  tjb9np7JDJmlCP-692j-Y  XmW7voiewTM-CT-USn1j0
0e0muxg6NgDObX-nnuHkQ  94MZIUTvQsAAPTQe4VlBg  d3mOZQdxg-4JGq56bs46c  h25DLE764BJJn7KIAgu9D  kUcTm-GPu45cRHlS5r1Pt  oYMQH1ho73juKAqtI908D  rBtfR71BQhteHunp208qy  tNFuTOhFYyW3Fp44K_CfL  -XPDIkLodsKnkc1RjccDn
0VJ7RwIXKc9RwDqsoLRMv  9a6MqAVKMQHAPoGmltChX  DJ1m35492spJ9xaE70liN  h6HqMDnmLIIdmKt_BZBpI  L0va4tyvLOUPgQ-Yegmpd  p3H8kxJkqw8lMDTGXhpOR  rDEmnF6-SeqJ_fblVWJj5  Ts1LbNjHbasVRh-twiNdm  xSegOEhCKa-4K6-z4rh4g
1ohuVoZNeZW-5Q2JZ-BMx  aA3MNfKlHnNzFKHzWPV6w  DMPFPFXdmCt5kjzLs9ksG  hL3r0FiplW2TAvrWq8pnT  ld_9GoGJ3meVc-RR414dV  pJX_9hD9EsHAIBDx79Q_2  Rl8YwqIlI5yNhpAk8ybml  Tspc0O5SrVytKm0E0URjl  xsux4qmgyjbBpVYiaDZC7
1V5AvaJ_K6PhMZ-ksFg8G  Abt37SBbeszZYffFkAdOq  dQl5Gc2k856dWbV449nZ-  hMcUiSDm-XEUfjprYffFe  lFfCvtkkMPfrlBl5RxL1N  PNAu_4u2t7Pk0BN5pXInH  rMb23BDGx5VA0WLE8VBOW  U0t9GMnQTTgVaXk3jXaml  XUo062rtpd6WRcz1jWX1U
_34EBmUORqyYL3qTLH7o6  aLF6F3FLX4q-_-Ufr8cxf  DWFxw0xbdhI69c9vTPzFM  hQguFJfU_Ageu1t9JgeRo  lJ3dT7nKEmmoWMhWkATAs  pV6RjH4_44FwBxTrx0QEd  rw1gmDKZ8x-1MZtrJWJ7S  U8A0p663tuYVf_UsZVBXk  xXzJuQgImtV4K7fIQfIDe
3Fy0dDvPkg570X-QZ_XqJ  ax0BUP1HG7Rn7Ae0F5nIw  f3JlunCrLJOJgWQ6ldFMr  I22QEgiL0nUWl3pyuNfM0  lPeOTzCelclsUh3k9ZLn7  pxGBon79a7RpKU_7tKJrb  RxUDVQBDL5cJtBdXiKM8E  UBSxBSzVkaxdhSPsEI1E0  Y3kuOHZU0yZJpCgXsA5xI
3wD_Kao_IU9SWi4SkeSdD  B75OLttmWDgT83DqOm-cm  Fg_zgTXWGC7N2tDrIuILS  I2NbtVumPwlnFOtTJDMgd  M9hVu-_yW618JZXbRhq-W  pXQS8nybeC3tdt3GGsN7B  RYnIXvxVhh7q-tvFBzkXz  uRGOCWnFLemuxUKFjmYIW  YbqVBoTPTyA5r6QEJmNAy
4pOFbA9V8jzboO7NfCbWG  BPj6c0ozB9hOE-Ye15tFd  Fhg1hL5Ncdcghvvyiwg_b  I5ba1ZmAFIQRafoYYn3JY  Ma5sXDPh7BGnJcZi2Ybfm  pYMIIqCyk83ZxMWq-V0ku  RZbL-JRvrw1_ZEg0BaEuu  UxW54QfLq090Mf4REWq9H  ycmTH-8VnODKosTcx0vTg
4QtRuw-0fai3Wnm15y2F3  BwfeensvGnswUT05mUi2C  flL2mJ5LNUNe5SK-7XuDS  I66TvVbwu9FDHbrfhdtPx  mmHDuFWhVRZAs3Jw0sZLA  QAzZnjTRs36dvx3ovsKNd  S1eQNWNGvh8UiqosPj-Ma  Vb7BN4UKiorWkH8X9MsWR  _YIX8Q-BLABTbmsEjPcjK
50CHeFpZkuHa00Bros7_-  Bw_FY0cYlGq-vTYVSf5qF  fMOKbKGN19zISvDbB_ARu  IdZrfvHKchnpAb32cOiP8  MyAwaMq7p5sk8Hw7rbUsi  Qf7Il7xo_NZE9kChutCpK  S2oTtebMp-XzGVMD_235n  VJc2UBw007cHqCsRqDBRD  yyLh7HNTUDUWOAFrHIcNw
59pnplcSvTe8rGFRfRwam  BxNlUqC49CL-lbMD-Vaq6  fRHtUlAkh_qMrWAGG6IBW  ie7ahyROXLftAm-6X6Uxr  MzMh2CpSfrWtdwr2Z5Owp  Qh1KzCbkL2-IlenUU6ExL  s95EVqbapXGdrcdkkmRpq  VyCzmtPB63OP_TZkNzXyB  YYP2pqc2WiL-Fdwogdhqk
_5feECxioTfXcW2eGp6rJ  c0x8NP1gGWRor49SAFIbR  ftFVIUhvhdU0GdbgQP-y-  ik--frWh2bgMqn5on3WDl  nhYG9xm9IBUljRE5UTGrO  qODwIpUiTjIE_m4WtsN1v  sbUYM7QIxkcBX6NUSeWPs  WNBjjZWpzqvDRJugVObnE  YZH0cWNLy7ZnVq9lQ0xkR
5gvQRgf5u1NxGo4j_ITms  C8S7fo0-L9diAnJwWFkNd  fyqMn32Hr_TL9Bjpvo2WA  il9cAGEGB8VTsiiaWqdUp  Np1Tk4QjWxXaS1XQ6LtpJ  qTb2y5tIq3KelJfxf2dyy  sskF4QwWoLR2KrMv12F8S  wV2gBxYRHz_dM4pR04-LI  zcL5cxFprsxjd-WcH5Vlo
68QZdQwW2-NL9gyeSdJPX  CGFbqpsude8U12MOKjWAH  g5XyvgYB8Nqrc5Pm-_BW-  iZ6YlyEHdO_NG7Xo-MoNK  NTaUvWb2YpMmnMWn_Pe_v  qTlDbnQFJ8q8yf5UY4uL2  SSO8MO30VR2KkmwPvGSjb  wVDyozBw7-i3xLU9AtpEy  ZeLc2h26z_aADMHrD8srh
7bB2zrvpHSiE6exrLGpe-  cIqg78L5-ejSPkAjMoVsR  gCEjsMAMxMm_oCunGLwT7  J5W1FW7IYWXJEJBvWCGct  Nx3f15B5tyBKhJpggD-wA  qWitc3Lb6EF9lGpQ9vJWD  suac68Ltyi3HzrK19rpox  x4Uh2NOxOR0RfJNYXobPM  ZZOlmTaWivp0z4JNsna_j
-7EITpbHt6nsxWxoLMHYR  ClhfWrI-XneZmmiUna_t5  gjIk6ZVFDNnJcvMzQcgLH  Jk2pAjtzo-QfTfPqtbDrU  NzVvrgNys55n2SwCvm5nZ  r172LhAwS8o2YedjbmAOI  SzhPOZeLgvRWA4aTY_XDk  X8rRNftEIl_Y4VvCpSlSe
7xJInV_vwI1U5LOFi_5hF  cM-v7lOcB1TeqjLzvMoua  GNGsN1GOGU1PWzYKiWaHt  KiUXA6v531eqdl2CcUNsu  o48sa7d5DfpuZh9E0AiHV  R2Lf9Dg7ozbfRicx7AGSO  t1h0x9GIKhafqd1CsWNcT  XfhoZVzvavYdlflHdh48a
8LnOrn20lAOHvXVsl6UTi  cPMOneEkHMImzF8j8UULB  GNrdjMnJvrE0B70vvV9gP  knc2ArUcrZ0Qx5ThMO-iE  OU6sSvqTfLCq9pB26DlJ6  R3MSu0QOPNhIk97NwLV9i  t_dU2YAIcjUWNGss6zBij  XFYvduzlu9D6B9HTTtc_1
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls /home/ir-lawa1/.cache/uv/archive-v0/xSegOEhCKa-4K6-z4rh4g/numpy/_core/tests/
data                    test_array_interface.py               test_custom_dtypes.py  test__exceptions.py     test_limited_api.py     test_nep50_promotions.py  test_scalar_ctors.py    test_strings.py
examples                test_arraymethod.py                   test_cython.py         test_extint128.py       test_longdouble.py      test_numeric.py           test_scalarinherit.py   test_ufunc.py
_locales.py             test_arrayobject.py                   test_datetime.py       test_function_base.py   test_machar.py          test_numerictypes.py      test_scalarmath.py      test_umath_accuracy.py
_natype.py              test_arrayprint.py                    test_defchararray.py   test_getlimits.py       test_memmap.py          test_overrides.py         test_scalar_methods.py  test_umath_complex.py
test_abc.py             test_casting_floatingpoint_errors.py  test_deprecations.py   test_half.py            test_mem_overlap.py     test_print.py             test_scalarprint.py     test_umath.py
test_api.py             test_casting_unittests.py             test_dlpack.py         test_hashtable.py       test_mem_policy.py      test_protocols.py         test_shape_base.py      test_unicode.py
test_argparse.py        test_conversion_utils.py              test_dtype.py          test_indexerrors.py     test_multiarray.py      test_records.py           test_simd_module.py
test_array_api_info.py  test_cpu_dispatcher.py                test_einsum.py         test_indexing.py        test_multithreading.py  test_regression.py        test_simd.py
test_array_coercion.py  test_cpu_features.py                  test_errstate.py       test_item_selection.py  test_nditer.py          test_scalarbuffer.py      test_stringdtype.py
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ uv pip list
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ uv pip freeze
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ cd ..
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ mkdir airflow_t
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow_t  airflow_test  rabbitmqadmin  rabbitmq_conn.py
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ cd airflow_test
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ cd ..
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow_t  airflow_test  rabbitmqadmin  rabbitmq_conn.py
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ cd airflow_t
(airflow_test) [ir-lawa1@login-q-2 airflow_t]$ ls
(airflow_test) [ir-lawa1@login-q-2 airflow_t]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ├─▶ failed to write to file `/rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_t/.venv/CACHEDIR.TAG`
  ╰─▶ Quota exceeded (os error 122)
(airflow_test) [ir-lawa1@login-q-2 airflow_t]$ uv venv py_venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: py_venv
uv::venv::creation

  × Failed to create virtualenv
  ├─▶ failed to write to file `/rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_t/py_venv/lib/python3.12/site-packages/_virtualenv.py`
  ╰─▶ Quota exceeded (os error 122)
(airflow_test) [ir-lawa1@login-q-2 airflow_t]$ cd ..
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ cd airflow_test
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls -lh airflow.db
-rw-r-----+ 1 ir-lawa1 rds-mOlK9qn0PlQ-managers 556K Oct  7 12:51 airflow.db
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls -lh logs
total 4.0K
drwxrws---+ 3 ir-lawa1 rds-mOlK9qn0PlQ-managers 4.0K Oct  7 14:38 scheduler
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ ls -lh airflow.cfg
-rw-------+ 1 ir-lawa1 rds-mOlK9qn0PlQ-managers 86K Oct  8 08:15 airflow.cfg
(airflow_test) [ir-lawa1@login-q-2 airflow_test]$ cd ..
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ ls -lh airflow_test
total 652K
-rw-------+ 1 ir-lawa1 rds-mOlK9qn0PlQ-managers  86K Oct  8 08:15 airflow.cfg
-rw-r-----+ 1 ir-lawa1 rds-mOlK9qn0PlQ-managers 556K Oct  7 12:51 airflow.db
drwxrws---+ 3 ir-lawa1 rds-mOlK9qn0PlQ-managers 4.0K Oct  7 12:51 logs
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ ls -lh airflow_t
total 4.0K
drwxrws---+ 4 ir-lawa1 rds-mOlK9qn0PlQ-managers 4.0K Oct  8 09:19 py_venv
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ rm -rf airflow_t
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow_test  rabbitmqadmin  rabbitmq_conn.py
(airflow_test) [ir-lawa1@login-q-2 ir-lawa1]$ deactivate
[ir-lawa1@login-q-2 ir-lawa1]$ mkdir airflow_t
[ir-lawa1@login-q-2 ir-lawa1]$ cd airflow_t
[ir-lawa1@login-q-2 airflow_t]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
uv::venv::creation

  × Failed to create virtualenv
  ├─▶ failed to write to file `/rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_t/.venv/lib/python3.12/site-packages/_virtualenv.pth`
  ╰─▶ Quota exceeded (os error 122)
[ir-lawa1@login-q-2 airflow_t]$ cd ..
[ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow_t  airflow_test  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-2 ir-lawa1]$ rm -rf airflow_t
[ir-lawa1@login-q-2 ir-lawa1]$ cd airflow_test
[ir-lawa1@login-q-2 airflow_test]$ ls
airflow.cfg  airflow.db  logs
[ir-lawa1@login-q-2 airflow_test]$ cp airflow.cfg ..
[ir-lawa1@login-q-2 airflow_test]$ cd ..
[ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow.cfg  airflow_test  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-2 ir-lawa1]$ rm -rf airflow_test
[ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow.cfg  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-2 ir-lawa1]$ ls -lh rabbitmqadmin
-rwxrwxrwx+ 1 ir-lawa1 rds-mOlK9qn0PlQ-managers 39K Oct  4 16:38 rabbitmqadmin
[ir-lawa1@login-q-2 ir-lawa1]$ ls -lh rabbitmq_conn.py
-rw-rw----+ 1 ir-lawa1 rds-mOlK9qn0PlQ-managers 257 Oct  4 17:23 rabbitmq_conn.py
[ir-lawa1@login-q-2 ir-lawa1]$ ls -lh rabbitmqadmin
-rwxrwxrwx+ 1 ir-lawa1 rds-mOlK9qn0PlQ-managers 39K Oct  4 16:38 rabbitmqadmin
[ir-lawa1@login-q-2 ir-lawa1]$ ls -lh rabbitmq_conn.py
-rw-rw----+ 1 ir-lawa1 rds-mOlK9qn0PlQ-managers 257 Oct  4 17:23 rabbitmq_conn.py
[ir-lawa1@login-q-2 ir-lawa1]$ mkdir airflow_tets
[ir-lawa1@login-q-2 ir-lawa1]$ rm -rf airflow_tets
[ir-lawa1@login-q-2 ir-lawa1]$ mkdir airflow_te
[ir-lawa1@login-q-2 ir-lawa1]$ cd airflow_te
[ir-lawa1@login-q-2 airflow_te]$ ls
[ir-lawa1@login-q-2 airflow_te]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
[ir-lawa1@login-q-2 airflow_te]$ source .venv/bin/activate
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ uv pip install apache-airflow
Resolved 140 packages in 1.83s
░░░░░░░░░░░░░░░░░░░░ [0/140] Installing wheels...                                                                                                                                                                   warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: alembic-1.13.3-py3-none-any.http.whl (alembic==1.13.3)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/lFfCvtkkMPfrlBl5RxL1N/alembic/config.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_te/.venv/lib/python3.12/site-packages/alembic/config.py
  Caused by: Quota exceeded (os error 122)
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ uv pip cache purge
error: unrecognized subcommand 'cache'

Usage: uv pip [OPTIONS] <COMMAND>

For more information, try '--help'.
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ uv pip3 cache purge
error: unrecognized subcommand 'pip3'

  tip: a similar subcommand exists: 'pip'

Usage: uv [OPTIONS] <COMMAND>

For more information, try '--help'.
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ uv pip cache info
error: unrecognized subcommand 'cache'

Usage: uv pip [OPTIONS] <COMMAND>

For more information, try '--help'.
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ uv pip 
Manage Python packages with a pip-compatible interface

Usage: uv pip [OPTIONS] <COMMAND>

Commands:
  compile    Compile a `requirements.in` file to a `requirements.txt` file
  sync       Sync an environment with a `requirements.txt` file
  install    Install packages into an environment
  uninstall  Uninstall packages from an environment
  freeze     List, in requirements format, packages installed in an environment
  list       List, in tabular format, packages installed in an environment
  show       Show information about one or more installed packages
  tree       Display the dependency tree for an environment
  check      Verify installed packages have compatible dependencies

Cache options:
  -n, --no-cache               Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation [env: UV_NO_CACHE=]
      --cache-dir <CACHE_DIR>  Path to the cache directory [env: UV_CACHE_DIR=]

Python options:
      --python-preference <PYTHON_PREFERENCE>  Whether to prefer uv-managed or system Python installations [env: UV_PYTHON_PREFERENCE=] [possible values: only-managed, managed, system, only-system]
      --no-python-downloads                    Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]

Global options:
  -q, --quiet                      Do not print any output
  -v, --verbose...                 Use verbose output
      --color <COLOR_CHOICE>       Control colors in output [default: auto] [possible values: auto, always, never]
      --native-tls                 Whether to load TLS certificates from the platform's native certificate store [env: UV_NATIVE_TLS=]
      --offline                    Disable network access
      --no-progress                Hide all progress outputs
      --directory <DIRECTORY>      Change to the given directory prior to running the command
      --project <PROJECT>          Run the command within the given project directory
      --config-file <CONFIG_FILE>  The path to a `uv.toml` file to use for configuration [env: UV_CONFIG_FILE=]
      --no-config                  Avoid discovering configuration files (`pyproject.toml`, `uv.toml`) [env: UV_NO_CONFIG=]
  -h, --help                       Display the concise help for this command
  -V, --version                    Display the uv version

Use `uv help pip` for more details.
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ uv pip list
Package                                  Version
---------------------------------------- ------------
aiohappyeyeballs                         2.4.3
aiohttp                                  3.10.9
aiosignal                                1.3.1
anyio                                    4.6.0
apache-airflow-providers-common-compat   1.2.0
apache-airflow-providers-common-io       1.4.1
apache-airflow-providers-common-sql      1.17.1
apache-airflow-providers-fab             1.4.0
apache-airflow-providers-ftp             3.11.1
apache-airflow-providers-http            4.13.1
apache-airflow-providers-imap            3.7.0
apache-airflow-providers-smtp            1.8.0
apache-airflow-providers-sqlite          3.9.0
apispec                                  6.6.1
argcomplete                              3.5.1
asgiref                                  3.8.1
attrs                                    24.2.0
blinker                                  1.8.2
cachelib                                 0.9.0
certifi                                  2024.8.30
cffi                                     1.17.1
charset-normalizer                       3.3.2
click                                    8.1.7
clickclick                               20.10.2
colorama                                 0.4.6
colorlog                                 6.8.2
configupdater                            3.2
connexion                                2.14.2
cron-descriptor                          1.4.5
croniter                                 3.0.3
cryptography                             43.0.1
deprecated                               1.2.14
dill                                     0.3.9
email-validator                          2.2.0
flask                                    2.2.5
flask-babel                              2.0.0
flask-caching                            2.3.0
flask-jwt-extended                       4.6.0
flask-limiter                            3.8.0
flask-login                              0.6.3
flask-session                            0.5.0
flask-sqlalchemy                         2.5.1
flask-wtf                                1.2.1
frozenlist                               1.4.1
fsspec                                   2024.9.0
google-re2                               1.1.20240702
grpcio                                   1.66.2
gunicorn                                 23.0.0
h11                                      0.14.0
httpcore                                 1.0.6
httpx                                    0.27.2
idna                                     3.10
importlib-metadata                       8.4.0
importlib-resources                      6.4.5
inflection                               0.5.1
itsdangerous                             2.2.0
jinja2                                   3.1.4
jmespath                                 1.0.1
jsonschema                               4.23.0
jsonschema-specifications                2023.12.1
lazy-object-proxy                        1.10.0
limits                                   3.13.0
linkify-it-py                            2.0.3
lockfile                                 0.12.2
mako                                     1.3.5
markupsafe                               3.0.0
marshmallow                              3.22.0
marshmallow-oneofschema                  3.1.1
marshmallow-sqlalchemy                   0.28.2
mdurl                                    0.1.2
methodtools                              0.4.7
more-itertools                           10.5.0
multidict                                6.1.0
opentelemetry-api                        1.27.0
opentelemetry-exporter-otlp              1.27.0
opentelemetry-exporter-otlp-proto-common 1.27.0
opentelemetry-exporter-otlp-proto-grpc   1.27.0
opentelemetry-exporter-otlp-proto-http   1.27.0
opentelemetry-proto                      1.27.0
opentelemetry-sdk                        1.27.0
ordered-set                              4.1.0
packaging                                24.1
pathspec                                 0.12.1
pendulum                                 3.0.0
pluggy                                   1.5.0
prison                                   0.2.1
psutil                                   6.0.0
pycparser                                2.22
pygments                                 2.18.0
pyjwt                                    2.9.0
python-daemon                            3.0.1
python-dateutil                          2.9.0.post0
python-nvd3                              0.16.0
python-slugify                           8.0.4
pyyaml                                   6.0.2
referencing                              0.35.1
requests                                 2.32.3
requests-toolbelt                        1.0.0
rfc3339-validator                        0.1.4
rich                                     13.9.2
rich-argparse                            1.5.2
rpds-py                                  0.20.0
setproctitle                             1.3.3
setuptools                               75.1.0
six                                      1.16.0
sniffio                                  1.3.1
sqlalchemy                               1.4.54
sqlalchemy-jsonfield                     1.0.2
sqlalchemy-utils                         0.41.2
sqlparse                                 0.5.1
tabulate                                 0.9.0
tenacity                                 9.0.0
termcolor                                2.5.0
text-unidecode                           1.3
time-machine                             2.15.0
typing-extensions                        4.12.2
uc-micro-py                              1.0.3
unicodecsv                               0.14.1
universal-pathlib                        0.2.5
urllib3                                  2.2.3
wirerope                                 0.4.7
wrapt                                    1.16.0
wtforms                                  3.1.2
yarl                                     1.13.1
zipp                                     3.20.2
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ uv pip install apache-airflow
Resolved 140 packages in 436ms
░░░░░░░░░░░░░░░░░░░░ [0/15] Installing wheels...                                                                                                                                                                    warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: alembic-1.13.3-py3-none-any.http.whl (alembic==1.13.3)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/lFfCvtkkMPfrlBl5RxL1N/alembic/ddl/base.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_te/.venv/lib/python3.12/site-packages/alembic/ddl/base.py
  Caused by: Quota exceeded (os error 122)
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_te/.venv/lib/python3.12/site-packages/
aiohappyeyeballs                                        distutils-precedence.pth                       linkify_it                                                 requests_toolbelt-1.0.0.dist-info
aiohappyeyeballs-2.4.3.dist-info                        dns                                            linkify_it_py-2.0.3.dist-info                              rfc3339_validator-0.1.4.dist-info
aiohttp                                                 docutils                                       lockfile                                                   rfc3339_validator.py
aiohttp-3.10.9.dist-info                                email_validator                                lockfile-0.12.2.dist-info                                  rich
aiohttp.libs                                            email_validator-2.2.0.dist-info                mako                                                       rich-13.9.2.dist-info
aiosignal                                               flask                                          Mako-1.3.5.dist-info                                       rich_argparse
aiosignal-1.3.1.dist-info                               Flask-2.2.5.dist-info                          markdown_it                                                rich_argparse-1.5.2.dist-info
airflow                                                 flask_appbuilder                               markupsafe                                                 rpds
alembic                                                 flask_babel                                    MarkupSafe-3.0.0.dist-info                                 rpds_py-0.20.0.dist-info
anyio                                                   Flask_Babel-2.0.0.dist-info                    marshmallow                                                setproctitle
anyio-4.6.0.dist-info                                   flask_caching                                  marshmallow-3.22.0.dist-info                               setproctitle-1.3.3.dist-info
apache_airflow_providers_common_compat-1.2.0.dist-info  Flask_Caching-2.3.0.dist-info                  marshmallow_oneofschema                                    setproctitle.libs
apache_airflow_providers_common_io-1.4.1.dist-info      flask_jwt_extended                             marshmallow_oneofschema-3.1.1.dist-info                    setuptools
apache_airflow_providers_common_sql-1.17.1.dist-info    Flask_JWT_Extended-4.6.0.dist-info             marshmallow_sqlalchemy                                     setuptools-75.1.0.dist-info
apache_airflow_providers_fab-1.4.0.dist-info            flask_limiter                                  marshmallow_sqlalchemy-0.28.2.dist-info                    six-1.16.0.dist-info
apache_airflow_providers_ftp-3.11.1.dist-info           Flask_Limiter-3.8.0.dist-info                  mdit_py_plugins                                            six.py
apache_airflow_providers_http-4.13.1.dist-info          flask_login                                    mdurl                                                      slugify
apache_airflow_providers_imap-3.7.0.dist-info           Flask_Login-0.6.3.dist-info                    mdurl-0.1.2.dist-info                                      sniffio
apache_airflow_providers_smtp-1.8.0.dist-info           flask_session                                  methodtools-0.4.7.dist-info                                sniffio-1.3.1.dist-info
apache_airflow_providers_sqlite-3.9.0.dist-info         flask_session-0.5.0.dist-info                  methodtools.py                                             sqlalchemy
apispec                                                 flask_sqlalchemy                               more_itertools                                             SQLAlchemy-1.4.54.dist-info
apispec-6.6.1.dist-info                                 Flask_SQLAlchemy-2.5.1.dist-info               more_itertools-10.5.0.dist-info                            sqlalchemy_jsonfield
argcomplete                                             flask_wtf                                      multidict                                                  SQLAlchemy_JSONField-1.0.2.dist-info
argcomplete-3.5.1.dist-info                             flask_wtf-1.2.1.dist-info                      multidict-6.1.0.dist-info                                  sqlalchemy_utils
asgiref                                                 frozenlist                                     multidict.libs                                             SQLAlchemy_Utils-0.41.2.dist-info
asgiref-3.8.1.dist-info                                 frozenlist-1.4.1.dist-info                     nvd3                                                       sqlparse
attr                                                    frozenlist.libs                                opentelemetry                                              sqlparse-0.5.1.dist-info
attrs                                                   fsspec                                         opentelemetry_api-1.27.0.dist-info                         tabulate
attrs-24.2.0.dist-info                                  fsspec-2024.9.0.dist-info                      opentelemetry_exporter_otlp-1.27.0.dist-info               tabulate-0.9.0.dist-info
babel                                                   google                                         opentelemetry_exporter_otlp_proto_common-1.27.0.dist-info  tenacity
blinker                                                 google_re2-1.1.20240702.dist-info              opentelemetry_exporter_otlp_proto_grpc-1.27.0.dist-info    tenacity-9.0.0.dist-info
blinker-1.8.2.dist-info                                 greenlet                                       opentelemetry_exporter_otlp_proto_http-1.27.0.dist-info    termcolor
cachelib                                                greenlet-3.1.1.data                            opentelemetry_proto-1.27.0.dist-info                       termcolor-2.5.0.dist-info
cachelib-0.9.0.dist-info                                grpc                                           opentelemetry_sdk-1.27.0.dist-info                         text_unidecode
certifi                                                 grpcio-1.66.2.dist-info                        ordered_set                                                text_unidecode-1.3.dist-info
certifi-2024.8.30.dist-info                             gunicorn                                       ordered_set-4.1.0.dist-info                                time_machine
cffi                                                    gunicorn-23.0.0.dist-info                      packaging                                                  time_machine-2.15.0.dist-info
cffi-1.17.1.dist-info                                   h11                                            packaging-24.1.dist-info                                   _time_machine.cpython-312-x86_64-linux-gnu.so
_cffi_backend.cpython-312-x86_64-linux-gnu.so           h11-0.14.0.dist-info                           pathspec                                                   time_machine.libs
cffi.libs                                               httpcore                                       pathspec-0.12.1.dist-info                                  typing_extensions-4.12.2.dist-info
charset_normalizer                                      httpcore-1.0.6.dist-info                       pendulum                                                   typing_extensions.py
charset_normalizer-3.3.2.dist-info                      httpx                                          pendulum-3.0.0.dist-info                                   tzdata
charset_normalizer.libs                                 httpx-0.27.2.dist-info                         pkg_resources                                              uc_micro
click                                                   idna                                           pluggy                                                     uc_micro_py-1.0.3.dist-info
click-8.1.7.dist-info                                   idna-3.10.dist-info                            pluggy-1.5.0.dist-info                                     unicodecsv
clickclick                                              importlib_metadata                             prison                                                     unicodecsv-0.14.1.dist-info
clickclick-20.10.2.dist-info                            importlib_metadata-8.4.0.dist-info             prison-0.2.1.dist-info                                     universal_pathlib-0.2.5.dist-info
colorama                                                importlib_resources                            psutil                                                     upath
colorama-0.4.6.dist-info                                importlib_resources-6.4.5.dist-info            psutil-6.0.0.dist-info                                     urllib3
colorlog                                                inflection                                     psutil.libs                                                urllib3-2.2.3.dist-info
colorlog-6.8.2.dist-info                                inflection-0.5.1.dist-info                     pycparser                                                  _virtualenv.pth
configupdater                                           inflection.py                                  pycparser-2.22.dist-info                                   _virtualenv.py
ConfigUpdater-3.2.dist-info                             itsdangerous                                   pygments                                                   werkzeug
connexion                                               itsdangerous-2.2.0.dist-info                   pygments-2.18.0.dist-info                                  wirerope
connexion-2.14.2.dist-info                              jinja2                                         PyJWT-2.9.0.dist-info                                      wirerope-0.4.7.dist-info
cron_descriptor                                         jinja2-3.1.4.dist-info                         python_daemon-3.0.1.dist-info                              wrapt
cron_descriptor-1.4.5.dist-info                         jmespath                                       python_dateutil-2.9.0.post0.dist-info                      wrapt-1.16.0.dist-info
croniter                                                jmespath-1.0.1.dist-info                       python_nvd3-0.16.0.dist-info                               wrapt.libs
croniter-3.0.3.dist-info                                jsonschema                                     python_slugify-8.0.4.dist-info                             wtforms
cryptography                                            jsonschema-4.23.0.dist-info                    pytz                                                       wtforms-3.1.2.dist-info
cryptography-43.0.1.dist-info                           jsonschema_specifications                      PyYAML-6.0.2.dist-info                                     _yaml
daemon                                                  jsonschema_specifications-2023.12.1.dist-info  PyYAML.libs                                                yaml
dateutil                                                jwt                                            re2                                                        yarl
deprecated                                              lazy_object_proxy                              referencing                                                yarl-1.13.1.dist-info
Deprecated-1.2.14.dist-info                             lazy_object_proxy-1.10.0.dist-info             referencing-0.35.1.dist-info                               zipp
dill                                                    lazy_object_proxy.libs                         requests                                                   zipp-3.20.2.dist-info
dill-0.3.9.dist-info                                    limits                                         requests-2.32.3.dist-info
_distutils_hack                                         limits-3.13.0.dist-info                        requests_toolbelt
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ rm -rf /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_te/.venv
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ deactivate
[ir-lawa1@login-q-2 airflow_te]$ ls
[ir-lawa1@login-q-2 airflow_te]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
[ir-lawa1@login-q-2 airflow_te]$ source .venv/bin/activate
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ pip install --no-cache apache-airflow
-bash: pip: command not found
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ uv pip install --no-cache apache-airflow
Resolved 140 packages in 3.36s
   Built python-nvd3==0.16.0
   Built unicodecsv==0.14.1
Prepared 139 packages in 1.97s
░░░░░░░░░░░░░░░░░░░░ [0/140] Installing wheels...                                                                                                                                                                   warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: markdown_it_py-3.0.0-py3-none-any.whl (markdown-it-py==3.0.0)
  Caused by: failed to copy file from /tmp/.tmpBijaMj/archive-v0/tjlqFxqkOe4zRSRGDeGvN/markdown_it/common/html_re.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow_te/.venv/lib/python3.12/site-packages/markdown_it/common/html_re.py
  Caused by: Quota exceeded (os error 122)
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ airflow
-bash: airflow: command not found
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ cd airflow_test
-bash: cd: airflow_test: No such file or directory
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ deactivate
[ir-lawa1@login-q-2 airflow_te]$ ls
[ir-lawa1@login-q-2 airflow_te]$ source .venv/bin/activate
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ ls
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ rm -rf .venv
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ rm -rf .venv
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ rm -rf .venv
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ rm -rf .venv
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ ls
(airflow_te) [ir-lawa1@login-q-2 airflow_te]$ deactivate
[ir-lawa1@login-q-2 airflow_te]$ ls
[ir-lawa1@login-q-2 airflow_te]$ cd ..
[ir-lawa1@login-q-2 ir-lawa1]$ las
-bash: las: command not found
[ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow.cfg  airflow_te  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-2 ir-lawa1]$ rm -rf airflow_te
[ir-lawa1@login-q-2 ir-lawa1]$ ls
airflow.cfg  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-2 ir-lawa1]$ cd ..
[ir-lawa1@login-q-2 rds-ukaea-ap002-mOlK9qn0PlQ]$ ls
Ansys           ir-bhat1  ir-cast3     ir-erka2-v2306  ir-horn3  ir-lan1   ir-mage1  ir-nobr1  ir-pame1  ir-quan1  ir-sidd1  ir-tiru1  ir-whit7    slurm-28064302.out
CRAsimulations  ir-bren1  ir-chap2     ir-erka2-v2312  ir-jack5  ir-lawa1  ir-mant2  ir-nunn1  ir-park1  ir-rath2  ir-star3  ir-tolk1  ir-zani1    tab53
dc-davi4        ir-broo2  ir-cumm2     ir-gadg1        ir-kerr2  ir-lewi4  ir-mars5  ir-osbo2  ir-parr3  ir-real1  ir-stef1  ir-turk1  mast        uda-install
ir-armi3        ir-byer1  ir-edge2     ir-harr6        ir-kryj2  ir-lykk1  ir-maso4  ir-otin1  ir-pate3  ir-sash1  ir-swan1  ir-wall2  mast-adios  ukaea-farscape
ir-atki2        ir-care1  ir-erka2-10  ir-hold2        ir-lahi1  ir-ma1    ir-miji1  ir-oztu1  ir-plow1  ir-shan1  ir-tind1  ir-watt2  raptor
[ir-lawa1@login-q-2 rds-ukaea-ap002-mOlK9qn0PlQ]$ Read from remote host login-icelake.hpc.cam.ac.uk: Operation timed out
Connection to login-icelake.hpc.cam.ac.uk closed.
client_loop: send disconnect: Broken pipe
ds2718@N0897-MAC ~ % ls
Desktop			Library			Pictures		airflow			first_works		intermediate_python	sshconnect
Documents		Movies			Public			dump.rdb		go			khalid			ukaea
Downloads		Music			agent.env		erl_crash.dump		hist_file.txt		python_airflow
ds2718@N0897-MAC ~ % ssh csd3

        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>
        <>                                                        <>
        <>                        !WARNING!                       <>
        <>                                                        <>
        <>                    RCS CSD3 Facility                   <>
        <>             Unauthorised Access Prohibited             <>
        <>    Use of this system constitutes acceptance of our    <>
        <>                     policies - see                     <>
        <> http://docs.hpc.cam.ac.uk/hpc/user-guide/policies.html <>
        <>                                                        <>
        <><><><><><><><><><><><><><><><><><><><><><><><><><><><><><>


(ir-lawa1@login-icelake.hpc.cam.ac.uk) TOTP Verification Code: 213944
Last login: Tue Oct  8 08:41:35 2024 from jump2.jet.uk
[ir-lawa1@login-q-1 ~]$ ls
rds  slurm_submit.peta4-cclake  slurm_submit.peta4-icelake  slurm_submit.wilkes3
[ir-lawa1@login-q-1 ~]$ cd rds
[ir-lawa1@login-q-1 rds]$ ls
rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-1 rds]$ cd rds-ukaea-ap002-mOlK9qn0PlQ
[ir-lawa1@login-q-1 rds-ukaea-ap002-mOlK9qn0PlQ]$ cd ir-lawa1
[ir-lawa1@login-q-1 ir-lawa1]$ ls
airflow.cfg  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-1 ir-lawa1]$ vim rabbitmqadmin
[ir-lawa1@login-q-1 ir-lawa1]$ mkdir airflow
[ir-lawa1@login-q-1 ir-lawa1]$ ls
airflow  airflow.cfg  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-1 ir-lawa1]$ cd airflow
[ir-lawa1@login-q-1 airflow]$ uv venv --python 3.12
Using CPython 3.12.6
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
[ir-lawa1@login-q-1 airflow]$ source .venv/bin/activate
(airflow) [ir-lawa1@login-q-1 airflow]$ uv pip install numpy
Resolved 1 package in 219ms
░░░░░░░░░░░░░░░░░░░░ [0/1] Installing wheels...                                                                                                                                                                     warning: Failed to hardlink files; falling back to full copy. This may lead to degraded performance.
         If the cache and target directories are on different filesystems, hardlinking may not be supported.
         If this is intentional, set `export UV_LINK_MODE=copy` or use `--link-mode=copy` to suppress this warning.
error: Failed to install: numpy-2.1.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.http.whl (numpy==2.1.2)
  Caused by: failed to copy file from /home/ir-lawa1/.cache/uv/archive-v0/xSegOEhCKa-4K6-z4rh4g/numpy/lib/tests/test_index_tricks.py to /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow/.venv/lib/python3.12/site-packages/numpy/lib/tests/test_index_tricks.py
  Caused by: Quota exceeded (os error 122)
(airflow) [ir-lawa1@login-q-1 airflow]$ ls /rds/project/rds-mOlK9qn0PlQ/ir-lawa1/airflow/.venv/lib/python3.12/site-packages/
numpy  _virtualenv.pth  _virtualenv.py
(airflow) [ir-lawa1@login-q-1 airflow]$ quota
Filesystem/Project    GB        quota     limit          grace           files    quota    limit   grace User/Grp/Proj
/home                  1.1       50.0      55.0                     -    ------- No File Quotas  ------- U:ir-lawa1
/rds-d2                0.0        0.0       0.0                     -        1        0        0       - G:rds
/rds-d5                0.0        0.0       0.0                     -        4        0        0       - G:ukaea-ap002
rds-mOlK9qn0PlQ   300010.0   300000.0  300000.0                     - 58789322 153600000 153600000       - P:90590
(airflow) [ir-lawa1@login-q-1 airflow]$ deactivate
[ir-lawa1@login-q-1 airflow]$ cd ..
[ir-lawa1@login-q-1 ir-lawa1]$ quota
Filesystem/Project    GB        quota     limit          grace           files    quota    limit   grace User/Grp/Proj
/home                  1.1       50.0      55.0                     -    ------- No File Quotas  ------- U:ir-lawa1
/rds-d2                0.0        0.0       0.0                     -        1        0        0       - G:rds
/rds-d5                0.0        0.0       0.0                     -        4        0        0       - G:ukaea-ap002
rds-mOlK9qn0PlQ   300010.0   300000.0  300000.0                     - 58789322 153600000 153600000       - P:90590
[ir-lawa1@login-q-1 ir-lawa1]$ cd ..
[ir-lawa1@login-q-1 rds-ukaea-ap002-mOlK9qn0PlQ]$ ls
Ansys           ir-bhat1  ir-cast3     ir-erka2-v2306  ir-horn3  ir-lan1   ir-mage1  ir-nobr1  ir-pame1  ir-quan1  ir-sidd1  ir-tiru1  ir-whit7    slurm-28064302.out
CRAsimulations  ir-bren1  ir-chap2     ir-erka2-v2312  ir-jack5  ir-lawa1  ir-mant2  ir-nunn1  ir-park1  ir-rath2  ir-star3  ir-tolk1  ir-zani1    tab53
dc-davi4        ir-broo2  ir-cumm2     ir-gadg1        ir-kerr2  ir-lewi4  ir-mars5  ir-osbo2  ir-parr3  ir-real1  ir-stef1  ir-turk1  mast        uda-install
ir-armi3        ir-byer1  ir-edge2     ir-harr6        ir-kryj2  ir-lykk1  ir-maso4  ir-otin1  ir-pate3  ir-sash1  ir-swan1  ir-wall2  mast-adios  ukaea-farscape
ir-atki2        ir-care1  ir-erka2-10  ir-hold2        ir-lahi1  ir-ma1    ir-miji1  ir-oztu1  ir-plow1  ir-shan1  ir-tind1  ir-watt2  raptor
[ir-lawa1@login-q-1 rds-ukaea-ap002-mOlK9qn0PlQ]$ cd ir-lawa
-bash: cd: ir-lawa: No such file or directory
[ir-lawa1@login-q-1 rds-ukaea-ap002-mOlK9qn0PlQ]$ cd ir-lawa1
[ir-lawa1@login-q-1 ir-lawa1]$ ls
airflow  airflow.cfg  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-1 ir-lawa1]$ myquota
-bash: myquota: command not found
[ir-lawa1@login-q-1 ir-lawa1]$ ls
airflow  airflow.cfg  rabbitmqadmin  rabbitmq_conn.py
[ir-lawa1@login-q-1 ir-lawa1]$ beegfs-ctl --getquota --mount=/airflow --gid ttrojan
-bash: beegfs-ctl: command not found
[ir-lawa1@login-q-1 ir-lawa1]$ vim airflow.cfg

#
# Variable: AIRFLOW__CORE__DAGBAG_IMPORT_ERROR_TRACEBACKS
#
dagbag_import_error_tracebacks = True

# If tracebacks are shown, how many entries from the traceback should be shown
#
# Variable: AIRFLOW__CORE__DAGBAG_IMPORT_ERROR_TRACEBACK_DEPTH
#
dagbag_import_error_traceback_depth = 2

# How long before timing out a DagFileProcessor, which processes a dag file
#
# Variable: AIRFLOW__CORE__DAG_FILE_PROCESSOR_TIMEOUT
#
dag_file_processor_timeout = 50

# The class to use for running task instances in a subprocess.
# Choices include StandardTaskRunner, CgroupTaskRunner or the full import path to the class
# when using a custom task runner.
#
# Variable: AIRFLOW__CORE__TASK_RUNNER
#
task_runner = StandardTaskRunner

# If set, tasks without a ``run_as_user`` argument will be run with this user
# Can be used to de-elevate a sudo user running Airflow when executing tasks
#
# Variable: AIRFLOW__CORE__DEFAULT_IMPERSONATION
#
default_impersonation = 

# What security module to use (for example kerberos)
#
# Variable: AIRFLOW__CORE__SECURITY
#
security = 

# Turn unit test mode on (overwrites many configuration options with test
# values at runtime)
#
# Variable: AIRFLOW__CORE__UNIT_TEST_MODE
#
unit_test_mode = False

# Whether to enable pickling for xcom (note that this is insecure and allows for
# RCE exploits).
#
# Variable: AIRFLOW__CORE__ENABLE_XCOM_PICKLING
#
enable_xcom_pickling = False

# What classes can be imported during deserialization. This is a multi line value.
# The individual items will be parsed as a pattern to a glob function.
# Python built-in classes (like dict) are always allowed.
#
# Variable: AIRFLOW__CORE__ALLOWED_DESERIALIZATION_CLASSES
#
allowed_deserialization_classes = airflow.*

# What classes can be imported during deserialization. This is a multi line value.
# The individual items will be parsed as regexp patterns.
# This is a secondary option to ``[core] allowed_deserialization_classes``.
#
                                                                                                                                                                                                  202,1          6%
