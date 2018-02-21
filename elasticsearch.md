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
