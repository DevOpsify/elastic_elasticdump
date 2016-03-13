## Export
docker run -t devopsifyinc/elastic_elasticdump --input=http://localhost:9200/.kibana --output=$ --searchBody '{"filter": { "or": [ {"type": {"value": "dashboard"}}, {"type" : {"value":"visualization"}}] }}'  > /tmp/kibana.json

## Import
docker run --rm -it -v /tmp/kibana.json:/tmp/kibana.json devopsifyinc/elastic_elasticdump --type=data --input=/tmp/kibana.json --output=http://localhos:9200/.kibana
