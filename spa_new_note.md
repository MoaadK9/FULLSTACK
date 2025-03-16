```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User types a note and clicks "Save"

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: { "message": "note received" }
    deactivate server

    Note right of browser: JavaScript updates the UI without reloading the page
    browser->>browser: Add new note to the list in memory
    browser->>browser: Re-render the note list dynamically
