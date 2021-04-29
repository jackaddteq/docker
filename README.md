# docker

```
 curl --unix-socket /var/run/docker.sock http://localhost/containers/brave_wing/stats

{"read":"2021-04-29T22:44:58.621590109Z","preread":"0001-01-01T00:00:00Z","pids_stats":{"current":2},"blkio_stats":{"io_service_bytes_recursive":[{"major":8,"minor":0,"op":"Read","value":0},{"major":8,"minor":0,"op":"Write","value":8192},{"major":8,"minor":0,"op":"Sync","value":4096},{"major":8,"minor":0,"op":"Async","value":4096},{"major":8,"minor":0,"op":"Discard","value":0},{"major":8,"minor":0,"op":"Total","value":8192}],"io_serviced_recursive":[{"major":8,"minor":0,"op":"Read","value":0},{"major":8,"minor":0,"op":"Write","value":2},{"major":8,"minor":0,"op":"Sync","value":1},{"major":8,"minor":0,"op":"Async","value":1},{"major":8,"minor":0,"op":"Discard","value":0},{"major":8,"minor":0,"op":"Total","value":2}],"io_queue_recursive":[],"io_service_time_recursive":[],"io_wait_time_recursive":[],"io_merged_recursive":[],"io_time_recursive":[],"sectors_recursive":[]},"num_procs":0,"storage_stats":{},"cpu_stats":{"cpu_usage":{"total_usage":74921743,"percpu_usage":[32312302,19205303,8643212,14760926],"usage_in_kernelmode":30000000,"usage_in_usermode":40000000},"system_cpu_usage":123986500000000,"online_cpus":4,"throttling_data":{"periods":0,"throttled_periods":0,"throttled_time":0}},"precpu_stats":{"cpu_usage":{"total_usage":0,"usage_in_kernelmode":0,"usage_in_usermode":0},"throttling_data":{"periods":0,"throttled_periods":0,"throttled_time":0}},"memory_stats":{"usage":3584000,"max_usage":3817472,"stats":{"active_anon":1486848,"active_file":0,"cache":0,"dirty":0,"hierarchical_memory_limit":9223372036854771712,"hierarchical_memsw_limit":0,"inactive_anon":0,"inactive_file":0,"mapped_file":0,"pgfault":4125,"pgmajfault":0,"pgpgin":1980,"pgpgout":1585,"rss":1507328,"rss_huge":0,"total_active_anon":1486848,"total_active_file":0,"total_cache":0,"total_dirty":0,"total_inactive_anon":0,"total_inactive_file":0,"total_mapped_file":0,"total_pgfault":4125,"total_pgmajfault":0,"total_pgpgin":1980,"total_pgpgout":1585,"total_rss":1507328,"total_rss_huge":0,"total_unevictable":0,"total_writeback":0,"unevictable":0,"writeback":0},"limit":16560922624},"name":"/brave_wing","id":"4956913d002852cbc709a1c9f56678fe86b50d74d08009e3532275461f1b032f","networks":{"eth0":{"rx_bytes":6351,"rx_packets":42,"rx_errors":0,"rx_dropped":0,"tx_bytes":0,"tx_packets":0,"tx_errors":0,"tx_dropped":0}}}

docker container stats

CONTAINER ID        NAME                CPU %               MEM USAGE / LIMIT     MEM %               NET I/O             BLOCK I/O           PIDS
4956913d0028        brave_wing          0.00%               3.418MiB / 15.42GiB   0.02%               7.48kB / 0B         0B / 8.19kB         2
17273f1398a8        funny_heisenberg    0.00%               3.281MiB / 15.42GiB   0.02%               14.4kB / 0B         0B / 8.19kB         2


 

```
