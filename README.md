# jjot

A minimal CLI for capturing thoughts instantly from the terminal.

```
$ jj
Note: Remember to check the API rate limits
Note added.
```

## Why jjot?

Sometimes you just need to write something down—fast. No apps to open, no files to name, no formatting to fuss with. Just `jj`, type, done.

jjot appends your thoughts to a single markdown file, perfect for [Obsidian](https://obsidian.md/) or any notes system.

## Install

```bash
# Clone the repo
git clone https://github.com/jacobaross/jjot.git

# Copy to your PATH
cp jjot/jj ~/.local/bin/

# Make sure ~/.local/bin is in your PATH
export PATH="$HOME/.local/bin:$PATH"
```

## Usage

### Quick note (append)

```bash
jj
```

Prompts for a note and appends it to `Quick Notes.md`:

```markdown
---

**Sat Dec 27 · 6:55 PM EST**

Remember to check the API rate limits
```

### New note (create file)

```bash
jj -n
```

Prompts for a title and body, creates a new file:

```markdown
# Meeting Notes

Discussion about Q1 roadmap

---
*Sat Dec 27 · 6:55 PM EST*
```

## Configuration

| Variable | Default | Description |
|----------|---------|-------------|
| `JJ_FILE` | `~/Documents/secondbrain/Quick Notes.md` | File for appending quick notes |
| `JJ_DIR` | Same directory as `JJ_FILE` | Directory for new note files |

```bash
# Example: use a different notes file
export JJ_FILE="$HOME/notes/inbox.md"
```

## Note Format

Each quick note includes:
- Horizontal rule separator (`---`)
- Timestamp with day, date, 12-hour time, and timezone
- Your note text

New standalone notes include:
- Title as H1 header and filename
- Body text
- Creation timestamp in footer

## License

MIT
