LiveReload is a development tool that automatically refreshes a web page in your browser whenever you make changes to your source files, such as HTML, CSS, or JavaScript. This streamlines the development process by providing immediate visual feedback, eliminating the need for manual browser refreshes.

### Flask
LiveReload’s [`livereload.Server`](https://livereload.readthedocs.io/en/latest/api.html#livereload.Server "livereload.Server") class can be used directly with Flask.

### Setup
Use the `livereload.Server` to serve the application.

### Usage
```Python
from livereload import Server

app = create_app()
app.debug = True  # debug mode is required for templates to be reloaded

server = Server(app.wsgi_app)
server.watch(...)
server.serve()
```