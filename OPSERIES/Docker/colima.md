# COLIMA

Colima is a lightweight, open-source alternative to Docker Desktop that runs Docker containers on macOS.

## TestContainer

I had some trouble using [TestContainer](https://github.com/GradedJestRisk/java-training/wiki/TestContainer) cause it looks for docker by default.
I use to have those env var in my `.zshrc`
```bash
export TESTCONTAINERS_DOCKER_SOCKET_OVERRIDE=/var/run/docker.sock
export TESTCONTAINERS_HOST_OVERRIDE=$(colima ls -j | jq -r '.address')
export DOCKER_HOST="unix://${HOME}/.colima/default/docker.sock"
```

But I recently had this new error:
```bash
Could not find a working container runtime strategy
```

I run TestContainer in debug mode to see more details:
```bash
DEBUG=testcontainers* npm test
```
to see that TestContainer was by default searching where Docker was supposed to be.
```bash
Error: getaddrinfo ENOTFOUND 192.168.106.2
```

So I change 
```bash
export TESTCONTAINERS_HOST_OVERRIDE=localhost
```

which brings us to another error, another default TestContainer behavior:
```bash
testcontainers [ERROR] Failed to pull image "alpine:latest": Error: Error from Docker credential provider: Error: spawn docker-credential-desktop ENOENT +0ms
```

To fix that, edit `~/.docker/config.json` file and remove `credsStore": "osxkeychain` entry.