# httparse

Takes http request as input and outputs the headers and their values as json. Exits just before reading the request body.

#### Dependency:

`bash`

(optional) `jq` 

#### Example

Run a simple http server in foreground in a terminal:

```bash
ncat \
-c './httparse >/dev/tty ;printf "HTTP/1.1 200 OK\r\n"; timeout 1 cat >/dev/tty' \
-kl 8080
```

In another terminal:

```bash
curl localhost:8080 -d "Hello server"$'\r\n'
```

See what you got in the first terminal :-)

