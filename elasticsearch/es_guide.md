# ElasticSearch GUIDE

NOTE: Below demo tests on ES 6.

## _mappings

[es mapping doc](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html)

```
Search the index 'testsdev'
curl -XGET "http://localhost:9200/testsdev/file/_mapping?pretty" -H "Content-Type: application/json; charset=utf-8"

Create a new index 'testsdev' and type is 'file'
curl -XPUT "http://localhost:9200/testsdev" -H "Content-Type: application/json; charset=utf-8" --data-binary '@C:\tests\tests_mappings.json'

Delete index 'testsdev'
curl -XDELETE "http://localhost:9200/testsdev" -H "Content-Type: application/json; charset=utf-8"
```

## _settings

```
Search settings parammters on index 'testsdev'
curl -XGET "http://localhost:9200/testsdev/_settings?pretty" -H "Content-Type: application/json; charset=utf-8"
```

## _cat

```
curl -XGET "http://localhost:9200/_cat?pretty" -H "Content-Type: application/json; charset=utf-8"

/_cat/nodes
/_cat/shards
/_cat/shards/{index}
/_cat/recovery
/_cat/recovery/{index}
/_cat/master
/_cat/indices
/_cat/indices/{index}
/_cat/thread_pool
/_cat/thread_pool/{thread_pools}/_cat/allocation
/_cat/plugins
/_cat/health
/_cat/templates
/_cat/segments
/_cat/segments/{index}
/_cat/snapshots/{repository}
/_cat/count
/_cat/count/{index}
/_cat/nodeattrs
/_cat/pending_tasks
/_cat/fielddata
/_cat/fielddata/{fields}
/_cat/repositories
/_cat/aliases
/_cat/aliases/{alias}
/_cat/tasks
```

### indices

```
curl -XGET "http://localhost:9200/_cat/indices?pretty" -H "Content-Type: application/json; charset=utf-8"
```

## _search

```
curl -XPOST "http://localhost:9200/testsdev/file/_search?pretty" -H "Content-Type: application/json; charset=utf-8" --data-binary '@C:\tests\tests_search_text.json'
```

## _delete_by_query

```
Delete data in index 'testsdev'
curl -XPOST "http://localhost:9200/testsdev/_delete_by_query" -H "Content-Type: application/json; charset=utf-8" --data-binary '@C:\tests\tests_delete_by_search.json'
```


## _update_by_query
[docs-update-by-query](https://www.elastic.co/guide/en/elasticsearch/reference/master/docs-update-by-query.html)
