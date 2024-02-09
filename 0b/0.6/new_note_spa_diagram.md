<!-- Create a diagram depicting the situation where the user creates a new note using the SPA version of the app -->
::: mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The browser executes the callback function onsubmit

    Note right of browser: The new note is pushed into the notes array, and the updated notes is rendered on the page

    Note right of browser: The new note is sent to the server as JSON data

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa

    Note left of server: The server receives the data as JSON string

    activate server
    server-->>browser: [ "content": "new note is created", "date": "2024-2-2"]
    deactivate server

    Note left of server: The server responds with status code 201 Created

:::