# TiddlyWiki Python API Wrapper

A Python wrapper for the TiddlyWiki WebServer API, allowing easy interaction with a TiddlyWiki server from Python applications.

## Features

- Comprehensive coverage of TiddlyWiki WebServer API endpoints
- Easy-to-use Pythonic interface
- Proper error handling with custom exceptions
- Support for authentication
- Type hinting for better IDE support

## Installation

You can install the TiddlyWiki Python API Wrapper using pip:

```bash
pip install tiddlywiki-api-wrapper
```

## Quick Start

Here's a simple example of how to use the TiddlyWiki API wrapper:

```
from tiddlywiki_api import TiddlyWikiAPI, TiddlyWikiAPIError

# Initialize the API client
api = TiddlyWikiAPI("http://your-tiddlywiki-url", username="your_username", password="your_password")

try:
    # Get all tiddlers
    tiddlers = api.get_all_tiddlers()
    print(f"Number of tiddlers: {len(tiddlers)}")

    # Create a new tiddler
    new_tiddler = {
        "title": "PythonTest",
        "text": "This is a test tiddler",
        "tags": ["test", "python"]
    }
    etag = api.put_tiddler("PythonTest", new_tiddler)
    print(f"Tiddler created successfully. ETag: {etag}")

    # Get the rendered content of a tiddler
    rendered_content = api.get_rendered_tiddler("PythonTest")
    print(f"Rendered content: {rendered_content[:100]}...")  # First 100 characters

except TiddlyWikiAPIError as e:
    print(f"An error occurred: {str(e)}")
```

## API Reference
For a complete list of available methods and their usage, please refer to the API Reference.

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## License
This project is licensed under the MIT License - see the LICENSE file for details.
