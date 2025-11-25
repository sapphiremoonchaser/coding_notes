## String -> Datetime
  
`dt = datetime.strptime("string", "format-code")`  
  
| Example String | Format Code |  
|----------------| ------------|
| "2025-03-10" | "%Y-%m-%d" |
| "03/10/2025" | "%m/%d/%Y" |
| "10-Mar-20205" | "%d-%b-%Y" |
| "2025/03/10 15:30" | "%Y/%m/%d %H%M" |
| "2025-03-10T15:30:00" | "%Y-%m-%dT%H:%M:%S"|
  
  
## Datetime -> String
  
`dt.strftime("%Y-%m-%d")`


