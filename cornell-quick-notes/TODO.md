# Database Setup

- [x] Create a notes table in your notes.db

- [x] Define the basic structure (id, title, created_at)

- [x] Set up SQLAlchemy in your Flask app

# Backend Steps (app.py)

- [x] Create a route to handle POST requests for new notes

- [x] Create a route to handle GET requests to fetch existing notes

- [x] Create a route to handle DELETE requests for removing notes

- [ ] Set up proper error handling for these routes

# Frontend Steps (notes.js)

Modify the existing addNote() function to:

- [ ] Capture the note title from the form

- [ ] Send a POST request to your backend

- [ ] Handle the response

- [ ] Update the UI with the new note

- [ ] Add functionality to:

- [ ] Load existing notes when the page loads

- [ ] Handle note deletion

- [ ] Update the sidebar list

# Testing Steps

- [ ] Test adding a new note

- [ ] Verify it appears in the database

- [ ] Verify it appears in the sidebar

- [ ] Test deleting a note

- [ ] Verify it's removed from both database and sidebar

# Error Handling

- [ ] Add validation for note titles

- [ ] Handle database connection errors

- [ ] Handle failed requests

- [ ] Provide user feedback for actions

# UI TODO

### Visual Feedback

- [x] Highlight the selected note in the sidebar

- [ ] Show a "Saving..." indicator when changes are being saved

- [ ] Add success/error notifications

### Form Field Management

- [x] Disable form fields when no note is selected

- [ ] Clear form fields when a note is deleted

- [ ] Add validation for important fields

### Error Handling

- [ ] Show user-friendly error messages

- [ ] Handle network errors gracefully

- [ ] Add retry logic for failed saves

### UI Polish

- [ ] Add loading states

- [ ] Smooth transitions

- [ ] Better mobile responsiveness


