# Database Setup

- [x] Create a notes table in your notes.db

- [x] Define the basic structure (id, title, created_at)

- [x] Set up SQLAlchemy in your Flask app

# Backend Steps (app.py)

- [x] Create a route to handle POST requests for new notes

- [x] Create a route to handle GET requests to fetch existing notes

- [x] Create a route to handle DELETE requests for removing notes

- [x] Set up proper error handling for these routes

# Frontend Steps (notes.js)

Modify the existing addNote() function to:

- [x] Capture the note title from the form

- [x] Send a POST request to your backend

- [x] Handle the response

- [x] Update the UI with the new note

Add functionality to:

- [x] Load existing notes when the page loads

- [x] Handle note deletion

- [x] Update the sidebar list

# Testing Steps

- [x] Test adding a new note

- [x] Verify it appears in the database

- [x] Verify it appears in the sidebar

- [x] Test deleting a note

- [x] Verify it's removed from both database and sidebar

# Error Handling

- [ ] Add validation for note titles

- [ ] Handle database connection errors

- [ ] Handle failed requests

- [ ] Provide user feedback for actions

# UI TODO

### Visual Feedback

- [x] Highlight the selected note in the sidebar

- [x] Show a "Saving..." indicator when changes are being saved

- [ ] Add success/error notifications

### Form Field Management

- [x] Disable form fields when no note is selected

- [x] Clear form fields when a note is deleted

- [ ] Add validation for important fields

### Error Handling

- [ ] Show user-friendly error messages

- [ ] Handle network errors gracefully

- [ ] Add retry logic for failed saves

### UI Polish

- [ ] Add loading states

- [ ] Smooth transitions

- [ ] Better mobile responsiveness

### Export Function


Markdown Format:
# {Topic}

Class: {class_name}
Date: {date}

## Main Points
{main_points_content}
## Notes
{notes_content}

## Summary
{summary_content}

# Considerations
Main points section will need to be configured as a bulleted list. Since this is a concise section in the Cornell Note Taking method I am thinking it would be good to set it to conenteditable so when the user types in a main key point and then they press enter it goes to the next bullet. The amount of main points the user can add will depend on what device they are on in terms of space that is available. The 3 main sections of this app that will have limited space in terms of what the user types will be in Main Points, Notes and Summary. Just like it would be if you were writing this information in a notebook. 

