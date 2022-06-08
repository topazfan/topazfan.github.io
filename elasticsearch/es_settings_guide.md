# _Settings GUIDE

## analysis

[es abaktsus doc](https://www.elastic.co/guide/en/elasticsearch/reference/master/analysis.html)


```
This is the segment of settings for analysis. It's defined two filter and to analyzer. filter is used on analyzer. analyzer is used on mapping define.

                "analysis": {
                    "filter": {
                        "snowball_filter": {
                            "type": "snowball",
                            "language": "English"
                        },
                        "synonym_filter": {
                            "type": "synonym",
                            "synonyms": [
                                "Germany, DE, DEU",
                                "France, FR, FRA",
                                "wegiel, coal"
                            ]
                        }
                    },
                    "analyzer": {
                        "index_analyzer": {
                            "filter": [
                                "standard",
                                "lowercase",
                                "snowball_filter"
                            ],
                            "tokenizer": "standard"
                        },
                        "synonym": {
                            "filter": [
                                "lowercase",
                                "synonym_filter",
                                "snowball_filter"
                            ],
                            "tokenizer": "standard"
                        }
                    }
                },
```

### analyzer 分析器

[create custom analyzer](https://www.elastic.co/guide/en/elasticsearch/reference/master/analysis-custom-analyzer.html)
[specify-analyzer](https://www.elastic.co/guide/en/elasticsearch/reference/master/specify-analyzer.html)
[analysis-analyzers](https://www.elastic.co/guide/en/elasticsearch/reference/master/analysis-analyzers.html)

As the settings segments of two analyzer 'index_analyzer' and 'synonym'. This can be used on mapping defined. like:

```
"fullname": {
   "type": "text",
   "analyzer": "index_analyzer",
   "search_analyzer": "synonym"
}
```

### tokenizer 分词器

[analysis-tokenizers](https://www.elastic.co/guide/en/elasticsearch/reference/master/analysis-tokenizers.html)

### token filter 标记过滤器

[analysis-tokenfilters](https://www.elastic.co/guide/en/elasticsearch/reference/master/analysis-tokenfilters.html)
```
This is defined that using naowball stemmer by using english language.
                        "snowball_filter": {
                            "type": "snowball",
                            "language": "English"
                        },
```

## unassigned

[delayed node](https://www.elastic.co/guide/en/elasticsearch/reference/current/delayed-allocation.html)
default is 1m

```
              "unassigned": {
                    "node_left": {
                        "delayed_timeout": "5m"
                    }
                }
```

