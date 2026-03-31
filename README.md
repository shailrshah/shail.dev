# shail.dev

A terminal-themed interactive resume and personal blog built with vanilla HTML, CSS, and JS.

**Live at:** [shail.dev](https://shail.dev) · [shailrshah.github.io](https://shailrshah.github.io)

## Features

- macOS-style desktop with dock, window chrome, and animated cursor
- Resume rendered as terminal commands (`whoami`, `cat summary.txt`, `./print_experience.sh`, etc.)
- Interactive command input with easter eggs (`sudo hire shail`, `man shail`, `diff junior.sh senior.sh`, and more)
- Blog with markdown rendering — posts listed in a Finder-style window, sorted by date
- Built-in contact form via mail window
- Single-window focus — opening an app minimizes others
- Mobile responsive with safe area support
- Print-friendly styles

## Structure

```
index.html        — HTML markup
style.css         — all styles
script.js         — interactive commands, animations, blog, mail form
blog/             — markdown blog posts
assets/           — favicon, app icons, and images
```

## Adding a blog post

1. Add a `.md` file to `blog/`
2. Register it in the `blogPosts` array in `script.js`:
   ```js
   { file: 'my-post.md', title: 'My Post', date: 'YYYY-MM-DD' }
   ```

## Run locally

```bash
python3 -m http.server 8080
```
