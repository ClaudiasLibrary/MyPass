![Logo](logo.png)
# MyPass
Made for Angela Yu's 100 days of code challenge

A simple password manager built with Python and Tkinter. This app allows users to:

- Generate secure random passwords.
- Save login credentials (website, email/username, and password).
- Retrieve saved credentials for a specific website.

The data is stored in a local `data.json` file to persist the credentials.

## Features

- **Password Generation**: Generate random passwords containing letters, numbers, and symbols.
- **Store Credentials**: Save credentials securely for different websites (email/username and password).
- **Retrieve Credentials**: Search and display saved credentials for a specific website.
- **Clipboard Support**: The generated password is automatically copied to the clipboard for easy use.

## Requirements

- Python 3.x
- Tkinter (comes pre-installed with Python)
- `pyperclip` library for clipboard functionality

### Installation

To install the required library (`pyperclip`), run:

```bash
pip install pyperclip
```

## How to Use

1. **Generate Password**: Click on the "Generate Password" button to generate a secure password, which will be copied to your clipboard.
2. **Save Credentials**: Enter the website, email/username, and password into the corresponding fields, and click "Add" to save your credentials.
3. **Search for Credentials**: Enter a website name and click the "Search" button to retrieve the saved email and password.

## Code Overview

### Password Generator
The `generate_password()` function generates a secure password by combining random letters, numbers, and symbols. The generated password is displayed in the password entry field and copied to the clipboard using the `pyperclip.copy()` function.

### Save Password
The `save()` function saves the credentials to a local JSON file (`data.json`). If the file doesn't exist, it is created. The new data is added to the existing data (if any) or a new file is written.

### Find Password
The `find_password()` function allows users to search for saved credentials by entering the website name. If found, the associated email/username and password are displayed in a popup message.

### UI Setup
The app uses `tkinter` to create a simple user interface. The main window contains:
- Entry fields for the website, email/username, and password.
- Buttons to generate a password, save credentials, and search for credentials.
- A logo image (ensure the `logo.png` image is in the same directory).

### JSON Data Structure
The credentials are stored in a JSON file with the following structure:

```json
{
  "example.com": {
    "email": "user@example.com",
    "password": "generated_password"
  }
}
```

### Error Handling
The app includes error handling for:
- Empty fields (when saving credentials).
- Missing `data.json` file (when searching for credentials).
- Searching for websites that do not have saved credentials.

## Customization

- **Email Default**: The default email inserted in the email entry field is `angela@gmail.com`. You can change this value as per your preference.
  
- **Logo**: Ensure you have a `logo.png` image in your project directory for the app's logo.

## License

This project is open source and available under the MIT License.

## Acknowledgments

- `pyperclip` for clipboard functionality.
- `tkinter` for the graphical user interface.
