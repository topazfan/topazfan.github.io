# MemcacheD

## MemcacheD memory model

Slab----1:N----Page----1:N---Chunk

[memory model](https://zhangbinalan.gitbooks.io/nosql/content/memcachede_nei_cun_mo_xing.html)

memcached -d -p 11211 -u memcached -m 2048 -c 1024 -P /var/run/memcached/memcached.pid -I 16

-m max memory size limit 
-c max thread num limit 
-I max each Page size limit (default 1M) 

## MemcacheD arguments

(protocol)[https://github.com/memcached/memcached/blob/master/doc/protocol.txt]

## How can check the keys
stats cachedump 1 10
stats cachedump [number of slab] [show numbers]

## MemcacheD distrubute

1. client distrubute
