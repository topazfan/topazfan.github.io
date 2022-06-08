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

### indices

## _search

## _delete_by_query


