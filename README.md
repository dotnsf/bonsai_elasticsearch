# Bonsai ElasticSearch

## Overview

- Try Bonsai ElasticSearch to use Japanese analysis and query.


## Prepare

- Index and Mappings

  - `my_suggest.json`

- Put index and mappings into my_suggest

  - `$ curl -XPUT https://username:password@xxxxxxxx.us-east-1.bonsaisearch.net:443/my_suggest -d @my_suggest.json -H 'Content-Type: application/json'`

- Data

  - `japanese.json`

- Post data into my_suggest

  - `$ curl -XPOST  https://username:password@xxxxxxxx.us-east-1.bonsaisearch.net:443/my_suggest/_bulk  --data-binary @japanese.json  -H 'Content-Type: application/x-ndjson'`


## Search Query

- 1. "日本"

  - Data

    - `query1.json`

  - Query

    - `$ curl -XGET https://username:password@xxxxxxxx.us-east-1.bonsaisearch.net:443/my_suggest/_search -d @query1.json -H 'Content-Type: application/json'`

  - Result

    - `result1.json`

- 2. "にほｎ"

  - Data

    - `query2.json`

  - Query

    - `$ curl -XGET https://username:password@xxxxxxxx.us-east-1.bonsaisearch.net:443/my_suggest/_search -d @query2.json -H 'Content-Type: application/json'`

  - Result

    - `result2.json`

- 3. "にｈん"

  - Data

    - `query3.json`

  - Query

    - `$ curl -XGET https://username:password@xxxxxxxx.us-east-1.bonsaisearch.net:443/my_suggest/_search -d @query3.json -H 'Content-Type: application/json'`

  - Result

    - `result3.json`

- 4. "にっほん"

  - Data

    - `query4.json`

  - Query

    - `$ curl -XGET https://username:password@xxxxxxxx.us-east-1.bonsaisearch.net:443/my_suggest/_search -d @query4.json -H 'Content-Type: application/json'`

  - Result

    - `result4.json`

- 5. "日本ん"

  - Data

    - `query5.json`

  - Query

    - `$ curl -XGET https://username:password@xxxxxxxx.us-east-1.bonsaisearch.net:443/my_suggest/_search -d @query5.json -H 'Content-Type: application/json'`

  - Result

    - `result5.json`


## References

https://www.elastic.co/jp/blog/implementing-japanese-autocomplete-suggestions-in-elasticsearch


