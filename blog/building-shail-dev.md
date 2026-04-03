# Building shail.dev

I wanted a personal website that felt like *me* — not a template, not a React app with a npm install away from 400 dependencies, not a Squarespace page. Just something I built from scratch that I was proud to share.

## The Concept

The idea was a macOS-style desktop with a terminal as the resume. Engineers spend half their lives in a terminal — it felt right. The resume renders as a sequence of shell commands: `whoami`, `cat summary.txt`, `./print_experience.sh --verbose`. There's an interactive input with easter eggs (`sudo hire shail`, `man shail`, `diff junior.sh senior.sh`). A blog window styled like Finder. A contact form that looks like composing an email.

No frameworks. No build tools. Just HTML, CSS, and JavaScript.

## The Stack

Deliberately minimal:

- **HTML/CSS/JS** — vanilla, no dependencies except a Google Font and `marked.js` for markdown rendering
- **Cloudflare Workers** — hosting with a built-in CDN, deploys on every push to `master`, preview URLs for every branch
- **Namecheap** — domain registration for `shail.dev`
- **SSL** — handled automatically by Cloudflare

The site is a single-page application, but every window has a real URL: `/resume`, `/contact`, `/blog`, `/blog/building-shail-dev`. Cloudflare's SPA routing serves `index.html` for all routes, and a small worker injects per-post OG tags so blog links preview correctly on WhatsApp, Slack, and iMessage. The JS reads `location.pathname` on load and opens the right window.

## The Hardest Part

Getting the layout right across desktop and mobile. The desktop icons and menu bar that look natural on a wide screen become clutter on a phone. On desktop, the icons sit fixed in the top-right corner. On mobile, they shift to a horizontal row below the menu bar — which disappears entirely to reclaim vertical space. It took several iterations to get both experiences feeling intentional rather than like one was an afterthought of the other.

## The Role of AI

I used AI for the entire build. Not just the hard parts — everything. The git log is the receipts: sound effects, cursor animations, the splash screen, the mail form, the blog, the dock, Safari fixes, mobile safe area padding, toast notifications, ghost autocomplete in the terminal. Every feature was a conversation.

That doesn't mean I wasn't driving. I made every design decision, reviewed every change, and pushed back when something was wrong — which happened often. But the execution was fully collaborative in a way that would have been impossible a few years ago.

The experience reinforced something I already believed: AI is most useful when you know exactly what you want and can evaluate what it produces. It accelerates execution — it doesn't replace judgment.

## What I'd Do Differently

- Be more deliberate about what you hand off to AI. It's fast, but every suggestion still needs review — and the cost of a bad one compounds quickly across a codebase you own.
- Skip the paid SSL cert. Cloudflare handles it for free.
- Start on Cloudflare Workers from day one instead of GitHub Pages. The SPA routing, CDN, preview branches, and wholesale domain pricing are all worth it — and the migration was more work than it needed to be.
- Define the scope before starting. Features like blog deep links got built, reverted, and left unfinished because the decision of whether to support them wasn't made upfront. Knowing what "done" looks like saves a lot of back-and-forth.

## The Result

A site I actually enjoy sharing. It loads fast, works on mobile, prints cleanly, and has a few surprises for anyone curious enough to poke around.

The best part isn't the animations or the easter eggs — it's that every line of it is mine. I know exactly why every decision was made, and I can change anything in minutes. That's a feeling no template can give you.
