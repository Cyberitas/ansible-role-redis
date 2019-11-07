Ansible Role: Redis
=========

Ansible role to install Redis on RHEL/CentOS

Requirements
------------

None.

Role Variables
--------------

Defualt variables for configuration (/defaults/main.yml):
```
redis_list_max_ziplist_size: -2
redis_stop_writes_on_bgsave_error: yes
redis_zset_max_ziplist_entries: 128
redis_hz: 10
redis_latency_monitor_threshold: 0
redis_repl_diskless_sync: no
redis_rdbcompression: yes
redis_notify_keyspace_events: ""
redis_list_compress_depth: 0
redis_aof_rewrite_incremental_fsync: yes
redis_repl_diskless_sync_delay: 5
redis_timeout: 0
redis_tcp_keepalive: 300
redis_appendonly: no
redis_protected_mode: yes
redis_dir: /var/lib/redis
redis_daemonize: no
redis_slave_read_only: yes
redis_slowlog_log_slower_than: 10000
redis_hll_sparse_max_bytes: 3000
redis_set_max_intset_entries: 512
redis_slowlog_max_len: 128
redis_pidfile: /var/run/redis_6379.pid
redis_loglevel: notice
redis_auto_aof_rewrite_percentage: 100
redis_slave_priority: 100
redis_lua_time_limit: 5000
redis_zset_max_ziplist_value: 64
redis_logfile: /var/log/redis/redis.log
redis_dbfilename: dump.rdb
redis_activerehashing: yes
redis_appendfsync: everysec
redis_repl_disable_tcp_nodelay: no
redis_rdbchecksum: yes
redis_tcp_backlog: 511
redis_supervised: no
#redis_bind: 127.0.0.1
redis_bind: 127.0.0.1
redis_appendfilename: "appendonly.aof"
redis_auto_aof_rewrite_min_size: 64mb
redis_slave_serve_stale_data: yes
redis_hash_max_ziplist_value: 64
redis_aof_load_truncated: yes
redis_client_output_buffer_limit:
  - normal 0 0 0
  - slave 256mb 64mb 60
  - pubsub 32mb 8mb 60
redis_save:
  - 900 1
  - 300 10
  - 60 10000
redis_port: 6379
redis_hash_max_ziplist_entries: 512
redis_no_appendfsync_on_rewrite: no
redis_databases: 16
```

The redis.conf.j2 template requires all of the above variables to exist.  By default they are declared  in /defaults/main.yml. Declaring  any of the default variables in host_vars, group_vars, or /var will override the default value.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: cyberitas.ansible_role_redis }

License
-------

MIT

Author Information
------------------

Created in 2019 by James Dugger for Cyberitas Technologies, LLC
