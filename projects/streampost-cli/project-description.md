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
