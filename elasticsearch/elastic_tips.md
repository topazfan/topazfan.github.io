

## max_inner_result_window

PUT http://localhost:9200/files/_settings
{
   "index.max_inner_result_window": 2147483647
}

## mappings setting

` 
Request to change the mappings via curl. if not use '@' for data file. It will cause errors:
{"error":{"root_cause":[{"type":"not_x_content_exception","reason":"Compressor detection can only be called on some xcontent bytes or compressed xcontent bytes"}],"type":"not_x_content_exception","reason":"Compressor detection can only be called on some xcontent bytes or compressed xcontent bytes"},"status":500}
`

ERROR example:
> curl -XPUT "http://localhost:9200/files/_mappings/file" -H "Content-Type: application/json; charset=utf-8" --data-binary 'C:\workspace\dev\es\files-settings.json'
> curl -XPUT "http://localhost:9200/files/_mappings/file" -H "Content-Type: application/json; charset=utf-8" --data 'C:\workspace\dev\es\files-settings.json'
NORMAL example:
> curl -XPUT "http://localhost:9200/files/_mappings/file" -H "Content-Type: application/json; charset=utf-8" --data-binary '@C:\workspace\dev\es\files-settings.json'

