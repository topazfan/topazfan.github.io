# MemcacheD

## MemcacheD memory model

Slab----1:N----Page----1:N---Chunk

[memory model](https://zhangbinalan.gitbooks.io/nosql/content/memcachede_nei_cun_mo_xing.html)

memcached -d -p 11211 -u memcached -m 2048 -c 1024 -P /var/run/memcached/memcached.pid -I 16

-m max memory size limit 
-c max thread num limit 
-I max each Page size limit (default 1M) 

## 数据清除

1. 懒惰过期清除策略
  内存不够的情况下先判定有过期数据就清除... 
2. LRU策略
  内存不够的情况下按照最近使用时间清除。（如果内存小的情况下，这是引起生产环境数据取不到的原因之一，因为被MemcacheD主动清除掉了。所以要慎重考虑使用场景，合理分配内存）
  
## MemcacheD arguments

[protocol](https://github.com/memcached/memcached/blob/master/doc/protocol.txt)

## How can check the keys
stats cachedump 1 10
stats cachedump [number of slab] [show numbers]

## MemcacheD distrubute

1. client distrubute
