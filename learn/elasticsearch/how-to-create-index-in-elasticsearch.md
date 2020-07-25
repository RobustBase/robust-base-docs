- [How to create Elasticsearch index using Postman](#how-to-create-elasticsearch-index-using-postman)
- [How to create Elasticsearch index using cURL](#how-to-create-elasticsearch-index-using-curl)
  - [Elasticsearch](#elasticsearch)
  - [Postman](#postman)



# How to create Elasticsearch index using Postman
# How to create Elasticsearch index using cURL

## Elasticsearch
- Navigate to Eleasticsearch installation/home directory
- Navigate to **bin** folder
- Run **elasticsearch.bat**
- Visit [http://localhost:9200](http://localhost:9200) URL, you will see response like mentioned below

  ```json
    {
     "cluster_name" : "xxxxxxxx",
     "status" : "green",
     "timed_out" : false,
     "number_of_nodes" : 2,
     "number_of_data_nodes" : 2,
     "active_primary_shards" : 15,
     "active_shards" : 12,
     "relocating_shards" : 0,
     "initializing_shards" : 0,
     "unassigned_shards" : 0,
     "delayed_unassigned_shards" : 0,
     "number_of_pending_tasks" : 0,
     "number_of_in_flight_fetch" : 0
    }
  ```

## Postman
- Launch Postman
