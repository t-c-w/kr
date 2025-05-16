# kr
Utils to work with json

To install:	```pip install kr```

## Overview
The `kr` package provides utility functions to handle JSON data, specifically focusing on error handling and reporting. It includes functions to convert error objects into dictionary or JSON format, optionally including traceback information to aid in debugging.

## Features
- **Error Object Serialization**: Convert exceptions and errors into a more readable and structured JSON format.
- **Traceback Inclusion**: Option to include traceback details in the serialized error output, which can be very helpful for debugging.

## Functions

### `get_dict_of_error_object(error_object, with_traceback=True)`
Converts an error object into a dictionary with keys for the error type and message. Optionally includes a traceback if `with_traceback` is set to `True`.

#### Parameters:
- **error_object**: The exception object to serialize.
- **with_traceback** (optional): Boolean flag to determine if traceback information should be included. Defaults to `True`.

#### Returns:
- A dictionary containing the error type, message, and optionally the traceback.

#### Example:
```python
try:
    1 / 0
except Exception as e:
    error_info = get_dict_of_error_object(e)
    print(error_info)
```

### `get_json_of_error_object(error_object)`
Converts an error object into a JSON string by utilizing `get_dict_of_error_object`.

#### Parameters:
- **error_object**: The exception object to serialize.

#### Returns:
- A JSON string representation of the error object.

#### Example:
```python
try:
    1 / 0
except Exception as e:
    error_json = get_json_of_error_object(e)
    print(error_json)
```

## Installation
Install the package using pip:
```bash
pip install kr
```

This package can be a useful tool in applications where error handling and reporting are crucial, especially in environments where JSON is the preferred format for data interchange.