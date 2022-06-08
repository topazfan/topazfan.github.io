# mappings GUIDE

[mapping doc](https://www.elastic.co/guide/en/elasticsearch/reference/master/mapping.html)

## dynamic

When Elasticsearch detects a new field in a document, it dynamically adds the field to the type mapping by default. The dynamic parameter controls this behavior.
[dynamic-field-mapping](https://www.elastic.co/guide/en/elasticsearch/reference/master/dynamic-field-mapping.html)

## type

Each field has a field data type, or field type. This type indicates the kind of data the field contains, such as strings or boolean values, and its intended use. For example, you can index strings to both text and keyword fields. However, text field values are analyzed for full-text search while keyword strings are left as-is for filtering and sorting.
[mapping-types](https://www.elastic.co/guide/en/elasticsearch/reference/master/mapping-types.html)

## analyzer

[mapping analyzer paramter](https://www.elastic.co/guide/en/elasticsearch/reference/master/analyzer.html)
[mapping search analyzer paramter](https://www.elastic.co/guide/en/elasticsearch/reference/master/search-analyzer.html)


## DEMO

### creating an index 'books' with 'chapter' 
```
curl -XPUT "http://localhost:9200/books" -H "Content-Type: application/json; charset=utf-8" --data-binary '@C:\tests\tests_mappings_books.json'
      {
          "mappings": {
            "book": {
                "dynamic": "false",
                "properties": {
                    "waitingApproval": {
                        "type": "keyword"
                    },
                    "sellto": {
                        "dynamic": "true",
                        "properties": {
                            "6-1111": {
                                "type": "boolean"
                            }
                      }
                    }
                    "createdDate": {
                        "type": "date"
                    },
                    "chapter": {
                        "type": "nested",
                        "properties": {
                            "name": {
                                "type": "text"
                            },
                            "fullname": {
                                "type": "text",
                                "analyzer": "index_analyzer",
                                "search_analyzer": "synonym"
                            },
                            "id": {
                                "type": "long"
                            },
                            "lastUpdated": {
                                "type": "date"
                            },
                            "terms": {
                                "properties": {
                                    "Access level-is": {
                                        "properties": {
                                            "term": {
                                                "type": "keyword"
                                            }
                                        }
                                    }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
```
