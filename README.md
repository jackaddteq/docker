# docker

- api stats
```
curl --unix-socket /var/run/docker.sock http://localhost/containers/nginx/stats
curl --cert /abc/cert.pem --cacert /abc/ca.pem --key /abc/key.pem https://192.168.199.100:2376/containers/nginx/stats

{"read":"2021-04-29T22:44:58.621590109Z","preread":"0001-01-01T00:00:00Z","pids_stats":{"current":2},"blkio_stats":{"io_service_bytes_recursive":[{"major":8,"minor":0,"op":"Read","value":0},{"major":8,"minor":0,"op":"Write","value":8192},{"major":8,"minor":0,"op":"Sync","value":4096},{"major":8,"minor":0,"op":"Async","value":4096},{"major":8,"minor":0,"op":"Discard","value":0},{"major":8,"minor":0,"op":"Total","value":8192}],"io_serviced_recursive":[{"major":8,"minor":0,"op":"Read","value":0},{"major":8,"minor":0,"op":"Write","value":2},{"major":8,"minor":0,"op":"Sync","value":1},{"major":8,"minor":0,"op":"Async","value":1},{"major":8,"minor":0,"op":"Discard","value":0},{"major":8,"minor":0,"op":"Total","value":2}],"io_queue_recursive":[],"io_service_time_recursive":[],"io_wait_time_recursive":[],"io_merged_recursive":[],"io_time_recursive":[],"sectors_recursive":[]},"num_procs":0,"storage_stats":{},"cpu_stats":{"cpu_usage":{"total_usage":74921743,"percpu_usage":[32312302,19205303,8643212,14760926],"usage_in_kernelmode":30000000,"usage_in_usermode":40000000},"system_cpu_usage":123986500000000,"online_cpus":4,"throttling_data":{"periods":0,"throttled_periods":0,"throttled_time":0}},"precpu_stats":{"cpu_usage":{"total_usage":0,"usage_in_kernelmode":0,"usage_in_usermode":0},"throttling_data":{"periods":0,"throttled_periods":0,"throttled_time":0}},"memory_stats":{"usage":3584000,"max_usage":3817472,"stats":{"active_anon":1486848,"active_file":0,"cache":0,"dirty":0,"hierarchical_memory_limit":9223372036854771712,"hierarchical_memsw_limit":0,"inactive_anon":0,"inactive_file":0,"mapped_file":0,"pgfault":4125,"pgmajfault":0,"pgpgin":1980,"pgpgout":1585,"rss":1507328,"rss_huge":0,"total_active_anon":1486848,"total_active_file":0,"total_cache":0,"total_dirty":0,"total_inactive_anon":0,"total_inactive_file":0,"total_mapped_file":0,"total_pgfault":4125,"total_pgmajfault":0,"total_pgpgin":1980,"total_pgpgout":1585,"total_rss":1507328,"total_rss_huge":0,"total_unevictable":0,"total_writeback":0,"unevictable":0,"writeback":0},"limit":16560922624},"name":"/brave_wing","id":"4956913d002852cbc709a1c9f56678fe86b50d74d08009e3532275461f1b032f","networks":{"eth0":{"rx_bytes":6351,"rx_packets":42,"rx_errors":0,"rx_dropped":0,"tx_bytes":0,"tx_packets":0,"tx_errors":0,"tx_dropped":0}}}
```
- docker container stats
```
docker container stats

CONTAINER ID        NAME                CPU %               MEM USAGE / LIMIT     MEM %               NET I/O             BLOCK I/O           PIDS
4956913d0028        brave_wing          0.00%               3.418MiB / 15.42GiB   0.02%               7.48kB / 0B         0B / 8.19kB         2
17273f1398a8        funny_heisenberg    0.00%               3.281MiB / 15.42GiB   0.02%               14.4kB / 0B         0B / 8.19kB         2
```
- docker system events
```
docker system events
2021-04-29T18:50:55.802621148-04:00 container create 01dfe8d8091366e7fbfada8259c90ef1efecef50598e33a5679f6b7370226835 (image=nginx, maintainer=NGINX Docker Maintainers <docker-maint@nginx.com>, name=inspiring_proskuriakova)
2021-04-29T18:50:55.804731772-04:00 container attach 01dfe8d8091366e7fbfada8259c90ef1efecef50598e33a5679f6b7370226835 (image=nginx, maintainer=NGINX Docker Maintainers <docker-maint@nginx.com>, name=inspiring_proskuriakova)
2021-04-29T18:50:55.838292713-04:00 network connect c03a2c332d8952831f404ffce9ade6666b80dfa2d5a4e5b77e95592ae7ae1401 (container=01dfe8d8091366e7fbfada8259c90ef1efecef50598e33a5679f6b7370226835, name=bridge, type=bridge)
2021-04-29T18:50:56.226307894-04:00 container start 01dfe8d8091366e7fbfada8259c90ef1efecef50598e33a5679f6b7370226835 (image=nginx, maintainer=NGINX Docker Maintainers <docker-maint@nginx.com>, name=inspiring_proskuriakova)


2021-04-29T18:51:09.360428752-04:00 container kill 01dfe8d8091366e7fbfada8259c90ef1efecef50598e33a5679f6b7370226835 (image=nginx, maintainer=NGINX Docker Maintainers <docker-maint@nginx.com>, name=inspiring_proskuriakova, signal=2)
2021-04-29T18:51:09.513820530-04:00 container die 01dfe8d8091366e7fbfada8259c90ef1efecef50598e33a5679f6b7370226835 (exitCode=0, image=nginx, maintainer=NGINX Docker Maintainers <docker-maint@nginx.com>, name=inspiring_proskuriakova)
2021-04-29T18:51:09.655520873-04:00 network disconnect c03a2c332d8952831f404ffce9ade6666b80dfa2d5a4e5b77e95592ae7ae1401 (container=01dfe8d8091366e7fbfada8259c90ef1efecef50598e33a5679f6b7370226835, name=bridge, type=bridge)

```
- cadvisor 
```
docker run -d --name=cadvisor -p 8080:8080 --volume=/var/run:/var/run:rw --volume=/var/lib/docker:/var/lib/docker:ro google/cadvisor:latest
http://localhost:8080
```
- remove all docker container

```
docker container rm -f $(docker container ls -aq)
```

