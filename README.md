# httparse

Takes http request as input and outputs the headers and their values as json. Exits just before reading the request body. Doesn't parse query parameters from the path though. It's on the TODO list.

#### Dependency:

`bash`

(optional) `mktemp` and `jq` 

#### Test-drive:

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

Now, open http://localhost:8080 in a browser and check the new output at the first terminal.

#### A simple Bash-script server using `httparse`:

The demo-server provided, uses `httparse`. Shows any POST/PUT payload on the server terminal, and greets client on GET.

Run the server on port 8080 as:

```bash
ncat -e './demo-server' -kl 8080
```

Open http://localhost:8080 in a browser.

Or, post a simple payload using cURL:

```bash
curl localhost:8080 -d "Hello server"
```

