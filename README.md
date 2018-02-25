# demo-gitlab-ci-docker-build

privilegedをtrueにしてある

```/etc/gitlab-runner/config.toml
concurrent = 1
check_interval = 0

[[runners]]
  name = "tdemo2 test"
  url = "http://gitlab.rf"
  token = "TOKEN"
  executor = "docker"
  [runners.docker]
    tls_verify = false
    image = "alpine:latest"
    privileged = true
    disable_cache = false
    volumes = ["/cache"]
    shm_size = 0
  [runners.cache]
```