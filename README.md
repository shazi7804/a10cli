# A10 command line tools

A10 load balance command line with API request.

https://www.a10networks.com/

## features

- support multiple environment.

- enable / disable real server status.

- check current connect.

- default get interface eth0/ens3 IP address that matches.

## Notice

- Default connection check retry 120 sec. (after exit 1)

## Require

- `a10cli.ini ` setting your environments.

```
# A10 command line tools config
# env tag: [ dev staging prod ]
ENV=dev
```

### Default reader order

`./a10cli.ini` > `scripts/a10cli.ini` > `/opt/.a10cli.ini`

## Usage

Auto control real server at A10.

- Get status

```
$ ./a10cli status
[200] server slb.server.fetchStatistics is enable
Current status: server is enable
session is close.
```

- status disable

```
$ ./a10cli stop
[200] server slb.server.update is disable
Current status: server is disable
session is close.
```

- status enable

```
$ ./a10cli start
[200] server slb.server.update is enable
Current status: server is enable
session is close.
```

- status enable after disable

```
$ ./a10cli restart
[200] server slb.server.update is disable
Current status: server is disable
[200] server slb.server.update is enable
Current status: server is enable
session is close.
```

- check no connect exists

```
$ ./a10cli overconn
The current connection is clean
session is close.
```
