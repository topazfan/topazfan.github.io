# ElasticSearch GUIDE

## _mappings

[es mapping doc](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html)

```
curl -XGET "http://localhost:9200/testsdev/file/_mapping?pretty" -H "Content-Type: application/json; charset=utf-8"

curl -XPUT "http://localhost:9200/testsdev" -H "Content-Type: application/json; charset=utf-8" --data-binary '@C:\tests\tests_mappings.json'

curl -XDELETE "http://localhost:9200/testsdev" -H "Content-Type: application/json; charset=utf-8"
```

## _settings

## _cat

### indices

## _search

## _delete_by_query


