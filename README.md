# 🌙 The Noctuary

**A Command-Line Journal for Dream Weavers and Lucid Explorers.**

The Noctuary is a powerful, terminal-based dream journal designed for those who want to keep a detailed record of their nightly adventures. It goes beyond simple note-taking, integrating with Google's Gemini AI to provide deep analysis, identify recurring themes, and actively assist in the practice of lucid dreaming.

The name comes from the word **noctuary**, which is a journal or record of things that pass in the night—a perfect description for this tool.

## Features

  - **✍️ Full Journaling Suite:** `add`, `edit`, `view`, and `delete` your dream entries with ease.
  - **✨ Enhanced CLI Readability:** Dream descriptions, reflections, and AI analyses are parsed from markdown into a clean, readable format. The output automatically wraps to your terminal's width, ensuring a perfect layout every time.
  - **🤔 Personal Reflection:** Add and edit your own personal analysis for each dream with the `reflect` command, keeping your thoughts separate from the AI's interpretation.
  - **📝 Rich Content Entry:** Uses your system's default text editor (`vim`, `nano`, `notepad`, etc.) for writing detailed, multi-line dream descriptions and analyses.
  - **🔎 Powerful Search & Listing:** `list` dreams by flexible date ranges (`7d`, `2025-08`, `2025-08-16`) and `search` your entire journal by keyword.
  - **🧠 AI-Powered Analysis:**
      - **Dream Interpretation:** Get a detailed analysis of a single dream's themes and symbolism with the `analyze` command.
      - **Trend Spotting:** Discover recurring dreamsigns, symbols, and emotions across multiple dreams with the `trends` command.
      - **MILD Mantra Generation:** Automatically create a personalized MILD (Mnemonic Induction of Lucid Dreams) mantra based on your last non-lucid dream using the `mantra` command.
      - **Auto-Tagging:** Automatically suggest relevant tags for your dream when you add it.
  - **📊 Detailed Statistics:** The `stats` command provides an overview of your dream history, including total dreams, lucid dream rate, average lucidity, and your most common tags.
  - **💻 CLI Native:** Fast, keyboard-driven, and designed to live in your terminal. Features color-coded output for excellent readability.
  - **⚙️ Cross-Platform Configuration:** Manages its configuration and database through a simple `config.ini` file located in the appropriate user-specific directory on Windows, macOS, and Linux.

## Installation

### Prerequisites

  - PHP 8.0+
  - The `php-sqlite3`, `php-curl`, and `php-mbstring` extensions.
  - A Google Gemini API Key (for AI features.)

### Steps

1.  **Clone the Repository**
    Clone this project to your local machine.

    ```sh
    git clone https://github.com/arthurdick/noctuary
    cd noctuary
    ```

2.  **Make the Script Executable**
    Give the script execute permissions.

    ```sh
    chmod +x noctuary
    ```

3.  **Place it in Your PATH (Recommended)**
    To use `noctuary` as a global command from anywhere in your terminal, move it to a directory in your system's PATH.

    ```sh
    sudo mv noctuary /usr/local/bin/
    ```

4.  **First Run & Configuration**
    The first time you run the script, it will automatically create a `config.ini` file and a `dream_journal.sqlite` database. You will need to edit the configuration file to add your API key. See the **Configuration** section below for details on where to find this file.

## Configuration

The Noctuary is configured via a simple `config.ini` file that is created automatically on the first run.

### Configuration File Location

  - **Linux:** `~/.config/noctuary/config.ini`
  - **macOS:** `~/.config/noctuary/config.ini`
  - **Windows:** `C:\Users\YourUser\AppData\Roaming\Noctuary\config.ini`

### Settings

Here is what the default `config.ini` file looks like:

```ini
[paths]
db_path = "/path/to/your/user/.local/share/noctuary/dream_journal.sqlite"

[api_keys]
gemini_api_key = ""
```

1.  **`db_path`**: The full path to your SQLite database file. You can change this to store your journal in a different location, such as a cloud-synced folder (e.g., Dropbox, Google Drive).
2.  **`gemini_api_key`**: Your Google Gemini API key.
      - Go to [Google AI Studio](https://aistudio.google.com/app/apikey) to create a new API key.
      - Paste the key into this file.

**Note:** The script can also use the `GEMINI_API_KEY` environment variable. If this variable is set, its value will be used *instead of* the key in the `config.ini` file.

## Usage

The Noctuary is controlled via simple commands. Here is a full list of available commands.

### Core Commands

| Command                                     | Description                                                                 |
| -------------------------------------------- | --------------------------------------------------------------------------- |
| `noctuary add [--date YYYY-MM-DD] [--auto-tag]` | Add a new dream entry. Opens your default editor for the description.         |
| `noctuary edit <id>`                         | Edit an existing dream entry by its ID.                                     |
| `noctuary delete <id>`                       | Permanently delete a dream entry by its ID.                                 |
| `noctuary view <id>`                         | Display the full details of a single dream, including its AI analysis.      |
| `noctuary reflect <id>`                      | Add or edit your personal analysis of a dream.                              |
| `noctuary search <keyword>`                  | Search titles, descriptions, and tags for a specific keyword.               |
| `noctuary stats`                             | Show detailed statistics about your dream history.                          |

### AI Commands

| Command                | Description                                                                    |
| ---------------------- | ------------------------------------------------------------------------------ |
| `noctuary analyze <id>`  | Perform an in-depth AI analysis on a single dream.                             |
| `noctuary trends [range]`| Analyze dreams in a date range to find recurring themes and dreamsigns.      |
| `noctuary mantra`      | Generate a personalized MILD mantra based on your last non-lucid dream.        |

### Utility Commands

| Command             | Description                                          |
| ------------------- | ---------------------------------------------------- |
| `noctuary help`     | Displays the help message with all available commands. |
| `noctuary version`  | Shows the current version of the script.             |

## License

This project is licensed under the MIT License.
