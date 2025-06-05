streampost-cli is an automated social media posting solution powered by Playwright. The user provides a list of social media content information preferably form an excel file that will scan and make posts accordingly. 

#### File Structure
```
streampost/
├── venv/                   ← Virtual Environment (Python environment isolation)
├── data/
│   ├── posts.xlsx          ← Spreadsheet containing post data per platform sheet
├── images/                 ← Folder containing images for posts
├── src/
│   ├── main.py             ← Entry point; orchestrates the workflow
│   ├── config.py           ← Configuration settings (creds, paths, etc.)
│   ├── spreadsheet_utils.py← Utility functions for reading/writing Excel
│   ├── playwright_utils.py ← Shared Playwright logic (login, upload, etc.)
│   └── platform_handlers/
│       ├── twitter_handler.py
│       ├── facebook_handler.py
│       └── linkedin_handler.py
├── requirements.txt        ← Python dependencies for the project
└── README.md               ← Project overview and usage instructions
```


#### Spreadsheet Structure
The structure of the spreadsheet creating post content will be as follows:

Post_ID: Unique identifier for each post (within this platform's sheet).
Content: The text content for the post on this platform.
Hashtags: Relevant hashtags.
Scheduled_Date: Date for scheduled posting (YYYY-MM-DD).
Post_Status: Status of the post (e.g., "Pending", "Success", "Failed").

For each platform like LinkedIn, Facebook etc. these will be contained within a dedicated sheet by the same name. That way each platform has it's own way of functioning limiting errors.


#### Spreadsheet Control Flow
```bash
START PROGRAM

  GET CURRENT DATE

  LOAD SPREADSHEET

  FOR EACH ROW in the SHEET:
    GET SCHEDULED DATE from the row
    GET POST STATUS from the row

    IF SCHEDULED DATE is EQUAL TO CURRENT DATE:
      IF POST STATUS is BLANK or "Pending":
        GET POST CONTENT, HASHTAGS, IMAGE, LINK from the row

        ATTEMPT TO POST to LinkedIn (using Playwright)

        IF POSTING WAS SUCCESSFUL:
          UPDATE POST STATUS in the spreadsheet to "Success"
        ELSE:
          UPDATE POST STATUS in the spreadsheet to "Failed"

  SAVE CHANGES TO SPREADSHEET

END PROGRAM
```