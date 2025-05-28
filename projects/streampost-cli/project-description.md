streampost-cli is an automated social media posting solution powered by Playwright. The user provides a list of social media content information preferably form an excel file that will scan and make posts accordingly. 

#### File Structure
```
streampost/
├── data/
│   ├── posts.xlsx
│   └── posted_items.txt
├── images/
├── src/
│   ├── main.py
│   ├── playwright_utils.py
│   ├── platform_handlers/
│   │   ├── twitter_handler.py
│   │   ├── facebook_handler.py
│   │   └── linkedin_handler.py
│   └── config.py
├── requirements.txt
└── README.md
```


#### Spreadsheet Structure
The structure of the spreadsheet creating post content will be as follows:

Post_ID: Unique identifier for each post (within this platform's sheet).
Content: The text content for the post on this platform.
Hashtags: Relevant hashtags.
Scheduled_Date: Date for scheduled posting (YYYY-MM-DD).
Post_Status: Status of the post (e.g., "Pending", "Posted Successful", "Failed").

For each platform like LinkedIn, Facebook etc. these will be contained within a dedicated sheet by the same name. That way each platform has it's own way of functioning limiting errors.