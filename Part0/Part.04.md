#Part 0.4
```mermaid
sequenceDiagram
  participant browser
  participant server

  browser->server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
  activate server
  server-->browser: Gives html doc
  deactivate server
  note right of server: request success status code:200
  browser->server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
  activate server
  server--> browser:Gives the css file
  deactivate server
  note right of server:status code:200
  browser->server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
  activate server
  server--> browser: js file
  deactivate server
  note left of browser: starts executing js code and requests json data from server
  browser->server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate server
  server-->browser:[...{content: " ",date:" "},..]
  deactivate server
  note left of browser: browser renders notes to display
  
 
  
  
