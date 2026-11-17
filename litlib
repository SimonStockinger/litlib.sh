#!/usr/bin/env bash

# Set your default directory here, or pass one as the first argument
srcDir="${1:-$HOME/Documents}"

# Verify the directory exists
if [[ ! -d "$srcDir" ]]; then
    echo "Error: Directory '$srcDir' does not exist." >&2
    exit 1
fi

# Find PDFs, strip the base path for a cleaner fzf view, and prompt selection
selected=$(find "$srcDir" -type f -iname "*.pdf" -printf "%P\n" 2>/dev/null | fzf --prompt="Select PDF: " --height=40% --layout=reverse --border)

# Exit cleanly if the user presses Esc or Ctrl+C
if [[ -z "$selected" ]]; then
    exit 0
fi

# Launch the selected PDF in Firefox detached from the terminal
nohup firefox "$srcDir/$selected" >/dev/null 2>&1 &
