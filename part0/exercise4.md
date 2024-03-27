sequenceDiagram
participant browser
participant server

browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
activate server
server->>browser: Redirect to main page
deactivate server
Note left of server: The input text is parsed by the JS code as a JSON and then rendered as a new note

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes.html
activate server
server->>browser: HTML document
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server->>browser: CSS File
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
activate server
server->>browser: JS File
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server->>browser: [{ "note": "camiones43" }]
deactivate server
Note right of browser: The browser calls the callback function that renders the note