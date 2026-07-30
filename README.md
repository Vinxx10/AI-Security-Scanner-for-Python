# Security Scanner

## 4-line explanation
This project scans a Python file and asks Gemini to review it for security issues.
`scanner.py` reads a target file, sends its contents to the model, and prints colored findings.
`vulnerable.py` contains example insecure patterns you can use for testing.
`test.py` lists available Gemini models using the same API key setup.

## What this project does
The scanner is a small command-line tool for spotting common code security problems such as SQL injection, hardcoded secrets, weak hashing, and unsafe command execution. It is designed for quick review of a single source file.

## Files
- `scanner.py`: Main scanner CLI.
- `vulnerable.py`: Sample intentionally vulnerable Python code.
- `test.py`: Helper script to list Gemini models available to your API key.

## Requirements
- Python 3.10+ recommended
- A Google Gemini API key
- Python packages:
  - `google-genai`
  - `python-dotenv`
  - `colorama`

## Setup
1. Create and activate a virtual environment.
2. Install dependencies:

```bash
pip install google-genai python-dotenv colorama
```

3. Create a `.env` file in the project root with your API key:

```env
GOOGLE_API_KEY=your_api_key_here
```

## How others use it
This is a local command-line tool, so each person runs it on their own machine with their own Gemini API key.

1. Clone the repository:

```bash
git clone <repo-url>
cd security_scanner
```

2. Set up Python and install dependencies:

```bash
python -m venv venv
source venv/bin/activate
pip install google-genai python-dotenv colorama
```

3. Create a `.env` file with their own key:

```env
GOOGLE_API_KEY=their_api_key_here
```

4. Run the scanner against any Python file:

```bash
python scanner.py vulnerable.py
```

## Usage
Scan a file:

```bash
python scanner.py vulnerable.py
```

List available Gemini models:

```bash
python test.py
```

## Notes
- `scanner.py` exits with an error if `GOOGLE_API_KEY` is missing.
- The scanner currently analyzes one file per run.
- Output severity labels are colorized for readability in the terminal.

## Example
Run the scanner against the included vulnerable sample:

```bash
python scanner.py vulnerable.py
```
