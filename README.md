# shail.dev

A terminal-themed interactive resume built with vanilla HTML, CSS, and JS.

**Live at:** [shail.dev](https://shail.dev) · [shailrshah.github.io](https://shailrshah.github.io)

## Features

- macOS-style desktop with dock, window chrome, and animated cursor
- Resume rendered as terminal commands (`whoami`, `cat summary.txt`, `./print_experience.sh`, etc.)
- Interactive command input with easter eggs (`sudo hire shail`, `man shail`, `diff junior.sh senior.sh`, and more)
- Built-in contact form via mail window
- Mobile responsive with safe area support
- Print-friendly styles

## Structure

```
index.html   — HTML markup
style.css    — all styles
script.js    — interactive commands, animations, mail form
```

## Run locally

```bash
python3 -m http.server 8080
```
