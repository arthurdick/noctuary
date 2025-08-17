# 🌙 The Noctuary

**A Command-Line Journal for Dream Weavers and Lucid Explorers.**

The Noctuary is a powerful, terminal-based dream journal designed for those who want to keep a detailed record of their nightly adventures. It goes beyond simple note-taking, integrating with Google's Gemini AI to provide deep analysis, identify recurring themes, and actively assist in the practice of lucid dreaming.

The name comes from the word **noctuary**, which is a journal or record of things that pass in the night—a perfect description for this tool.

## Features

  - **✍️ Full Journaling Suite:** `add`, `edit`, `view`, and `delete` your dream entries with ease.
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

## Installation

### Prerequisites

  - PHP 8.0+
  - The `php-sqlite3` and `php-curl` extensions.
  - A Google Gemini API Key (for AI features.)

### Steps

1.  **Clone the Repository**
    Clone this project to your local machine.

    ```sh
    git clone https://github.com/arthurdick/noctuary
    cd noctuary
    ```

2.  **Get Your API Key**

      - Go to [Google AI Studio](https://aistudio.google.com/app/apikey).
      - Create a new API key.
      - **Important:** Keep this key private and secure.

3.  **Set the Environment Variable**
    The script reads the API key from an environment variable called `GEMINI_API_KEY`. You must set this for any of the AI features to work.

    ```sh
    export GEMINI_API_KEY="YOUR_API_KEY_HERE"
    ```

    *Pro-tip: Add this line to your shell's startup file (`~/.zshrc`, `~/.bashrc`, or `~/.bash_profile`) to make it permanent.*

4.  **Make the Script Executable**
    Give the script execute permissions.

    ```sh
    chmod +x noctuary
    ```

5.  **Place it in Your PATH (Recommended)**
    To use `noctuary` as a global command from anywhere in your terminal, move it to a directory in your system's PATH.

    ```sh
    sudo mv noctuary /usr/local/bin/
    ```

6.  **First Run**
    The first time you run the script, it will automatically create the `dream_journal.sqlite` database file in the same directory.

## Usage

The Noctuary is controlled via simple commands. Here is a full list of available commands.

### Core Commands

| Command                                      | Description                                                                 |
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
