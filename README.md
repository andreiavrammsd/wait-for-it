# Wait for it

## Run a command only when port on host is available

### Tested on Alpine and Ubuntu

I needed to run a command in an Alpine Docker container only after another process (from other container) was open.

Based on https://github.com/vishnubob/wait-for-it. Many thanks!

Uses: https://en.wikipedia.org/wiki/Netcat

#### Setup
* chmod +x wait-for-it.sh
* Change shebang line as needed:
    * Alpine: #!/usr/bin/env sh
    * Ubuntu: #!/usr/bin/env bash

#### Usage
 
```
./wait-for-it.sh -h host -p port [-c command] [-t timeout] [-q quiet]
    -h          Host or IP under test
    -p          TCP port under test
    -c          Command to execute if test succeeds
    -t          Timeout in seconds, zero for no timeout
    -q          Don't output any status messages
```

#### Examples

```
./wait-for-it.sh -h www.google.com -p 80 -t 5 -c "echo Google is up" -q
```

```
./wait-for-it.sh -h www.google.com -p 8080 -t 5
```
