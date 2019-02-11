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

## Combine `or` and `exists` query

Say you want to everyone with gender `male` and those who haven't registered any gender.

```json
GET my_index/_search
{
  "query": {
    "bool": {
      "should": [
        {
          "bool": {
            "must_not": {
              "exists" : { "field" : "gender" }
            }
          }
        },
        {
          "bool": {
            "must": {"term": {"gender": "male"}}
          }
        }
        ]
    }
  }
}
```

Inside a `should` clause, we have two `bool` clauses.

## Update a single field

```json
POST /indexname/id/_update
{
  "doc": {
    "field_one": 1,
    "the_other_field": "Psychotherapeutism"
  }
}
```

## Discard on term value

Say you don't want results containing certain phone numbers.
```json
GET my_phone_numbers/_search
{
  "query": {
    "bool": {
      "must_not": [
        {"term": {
          "phone_number": {
            "value": 1200161
          }
        }},
        {"term": {
          "phone_number": {
            "value": 1000002
          }
        }}
      ]
    }
  },
  "size": 0,
  "aggs": {
    "my_aggregation_name": {
      "terms": {
        "field": "phone_number",
        "size": 100
      }
    }
  }
}
```


## Using high level REST client

If your ElasticSearch instance is not on `localhost:9200`, but say on `www.something.com/elastic`, then it is not obvious how to configure the high livel REST client. 

The `setPathPrefix` is necesarry to call something other than the rooot URL.

```java
return new RestHighLevelClient(RestClient.builder(
    new HttpHost("www.something.com", 443, "https")).setPathPrefix("/elastic"));
```
