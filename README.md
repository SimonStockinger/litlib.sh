# litlib - fzf PDF Launcher

A lightweight bash script to search for PDF files in a directory using `fzf` and open the selected file in Firefox.

## Prerequisites

Ensure the following tools are installed on your system:

* **`bash`** and **`find`** (pre-installed on most Linux distributions)
* **[`fzf`](https://github.com/junegunn/fzf)** (Command-line fuzzy finder)
* **Firefox** (`firefox` executable available in your `$PATH`)
* *Optional:* **`poppler-utils`** (provides `pdftotext` if using the live preview feature)

### Quick Install (Debian/Ubuntu)
```bash
sudo apt install fzf firefox poppler-utils
```

### Quick Install (Arch Linux)
```bash
sudo pacman -S fzf firefox poppler
```

### Quick Install (Fedora)
```bash
sudo dnf install fzf firefox poppler-utils
```

## Setup

1. **Save the script** to a directory in your `$PATH` (such as `~/.local/bin`):
   ```bash
   nano ~/.local/bin/open-pdf
   ```

2. **Make the script executable:**
   ```bash
   chmod +x ~/.local/bin/open-pdf
   ```

3. **Configure your default directory (Optional):**
   Open the script and update the `srcDir` fallback path (`$HOME/Documents` by default) to your preferred PDF folder.

## Usage

Run the script using your default directory:
```bash
open-pdf
```

Or pass a specific target directory as an argument:
```bash
open-pdf /path/to/your/pdfs
```

### Controls
* **Type** to filter the PDF list.
* **`Up` / `Down`** (or `Ctrl+K` / `Ctrl+J`) to navigate results.
* **`Enter`** to open the highlighted PDF in Firefox.
* **`Esc`** or **`Ctrl+C`** to cancel and exit.
