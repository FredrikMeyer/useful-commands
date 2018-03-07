# Elasticsearch

## Filter on term value

```json
GET index_name/_search
{
  "query": {
    "bool": {
      "must": [],
      "filter": [
        {"term": {"is_flowering": true }},
        {"term": {"name": "Florensis Absolutis"}}
          ]
      }
    }
  }
}
```

## Sort the response

```json
GET my_index/_search
{
  "sort": [
    {"timestamp" : {"order" : "desc"}}
    ]
}
```

## Match `or`

Extended example.

```json
GET my_index/_search
{
  "query": {
    "bool": {
      "should": [
        {"term": {
          "gender": "male"
        }},
        {"term": {
          "gender": "somewhat male"
        }}
      ]
    }
  },
  "_source": "gender",
  "aggs": {
    "genres": {
      "terms": {
        "field": "gender",
        "size": 10
      }
    }
  }
}
```

We only query for documents having `gender` equal to either `male` or `somewhat male`. Then we use `aggs` to list how many documents contained each `gender` type.