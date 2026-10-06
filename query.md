ContainerLogV2  
| where TimeGenerated > ago(300m)               // 1. Timestamp in the last 3 minutes  
| where LogLevel == "error"                     // 2. Error level filter  
| where PodName contains "order-api"            // 3. Pod name filter  
| extend parsedJson = iff(isnotnull(parse_json(LogMessage)), parse_json(LogMessage), dynamic(null))   // Safe JSON parsing  
| where tostring(parsedJson.message) contains "order_id_123456"                                       // 4. Extract and filter by a JSON key/value  
| project TimeGenerated, PodName, LogLevel, MessageSummary = tostring(parsedJson.message), LogMessage  
| sort by TimeGenerated desc                                                                         // 5. Sort by descending order (newest first)  
| take 10   
