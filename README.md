# redis

## Description
Ansible role to install and configure redis.

## Example Playbook
```YAML
---
- name: Redis
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: bubebyte.redis
```

## Role Variables
These are the role default which are set in default/main.yml:
```YAML
---
redis_instances:
  - name: redis
    configuration:
      bind: 127.0.0.1
      protected-mode: "yes"
      port: 6379
      tcp-backlog: 511
      timeout: 0
      tcp-keepalive: 300
      daemonize: "no"
      supervised: "no"
      pidfile: /var/run/redis_6379.pid
      loglevel: notice
      logfile: /var/log/redis/redis.log
      databases: 16
      always-show-logo: "yes"
      save:
        - "900 1"
        - "300 10"
        - "60 10000"
      stop-writes-on-bgsave-error: "yes"
      rdbcompression: "yes"
      rdbchecksum: "yes"
      dbfilename: dump.rdb
      dir: /var/lib/redis
      replica-serve-stale-data: "yes"
      replica-read-only: "yes"
      repl-diskless-sync: "no"
      repl-diskless-sync-delay: 5
      repl-disable-tcp-nodelay: "no"
      replica-priority: 100
      lazyfree-lazy-eviction: "no"
      lazyfree-lazy-expire: "no"
      lazyfree-lazy-server-del: "no"
      replica-lazy-flush: "no"
      appendonly: "no"
      appendfilename: '"appendonly.aof"'
      appendfsync: everysec
      no-appendfsync-on-rewrite: "no"
      auto-aof-rewrite-percentage: 100
      auto-aof-rewrite-min-size: 64mb
      aof-load-truncated: "yes"
      aof-use-rdb-preamble: "yes"
      lua-time-limit: 5000
      slowlog-log-slower-than: 10000
      slowlog-max-len: 128
      latency-monitor-threshold: 0
      notify-keyspace-events: '""'
      hash-max-ziplist-entries: 512
      hash-max-ziplist-value: 64
      list-max-ziplist-size: -2
      list-compress-depth: 0
      set-max-intset-entries: 512
      zset-max-ziplist-entries: 128
      zset-max-ziplist-value: 64
      hll-sparse-max-bytes: 3000
      stream-node-max-bytes: 4096
      stream-node-max-entries: 100
      activerehashing: "yes"
      client-output-buffer-limit:
        - "normal 0 0 0"
        - "replica 256mb 64mb 60"
        - "pubsub 32mb 8mb 60"
      hz: 10
      dynamic-hz: "yes"
      aof-rewrite-incremental-fsync: "yes"
      rdb-save-incremental-fsync: "yes"
```

## Requirements

### Roles
none

### Collections
none

## License
MIT License

## Author Information
[Armin Bube](https://bubebyte.de)
