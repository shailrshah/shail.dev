# UI Backlog

Ordered by impact (highest first).

---

### 1. Focus states on all interactive elements
**Priority:** Critical — Accessibility  
**Effort:** Low  

No visible focus indicators on dock icons, desktop icons, suggestion buttons, run button, or window dots. Keyboard users cannot tell what's focused.

**Fix:** Add `:focus-visible` outlines using `var(--cyan)` with a subtle offset. Apply globally to all interactive elements.

---

### 2. Splash login button focus ring
**Priority:** Critical — Accessibility  
**Effort:** Low  

The login button on the splash screen has no focus ring. It's the first interactive element on the page.

**Fix:** Add `:focus-visible` style to `.splash-btn` with a cyan outline matching the button border.

---

### 3. Menubar hidden on mobile
**Priority:** High — Functionality  
**Effort:** Medium  

`menubar` is `display: none` on mobile. The lock icon and clock are completely inaccessible.

**Fix:** Either show a simplified menubar on mobile, or move the lock icon into the dock and the clock into the desktop area.

---

### 4. Firefox scrollbar styling
**Priority:** Medium — Visual consistency  
**Effort:** Low  

Terminal scrollbar is only styled for WebKit (`::-webkit-scrollbar`). Firefox users see the default OS scrollbar.

**Fix:** Add `scrollbar-width: thin; scrollbar-color: var(--border) var(--bg);` to `.terminal`.

---

### 5. Inline styles → CSS classes (mail/blog windows)
**Priority:** Medium — Maintainability  
**Effort:** Low  

The mail window and blog finder have positioning and sizing as inline `style` attributes in HTML. Hard to override and easy to miss when editing.

**Fix:** Extract to `.mail-window` and `.blog-finder` classes in `style.css`. Remove all inline styles from those elements.

---

### 6. Accessible labels on dock icons
**Priority:** Medium — Accessibility  
**Effort:** Low  

Dock icon SVGs have no `aria-label` or `role`. Screen readers can't identify them. The text labels below are not programmatically associated.

**Fix:** Add `role="button"` and `aria-label` to each dock icon div (e.g., `aria-label="Open Resume"`).

---

### 7. Music widget hover state
**Priority:** Low — Polish  
**Effort:** Low  

Desktop icons lift on hover (`translateY(-4px)`) but the music widget has no hover feedback.

**Fix:** Add a subtle glow or scale on `.music-widget:hover` (e.g., `filter: brightness(1.1)` or ring stroke opacity change).

---

### 8. Blog file row active/pressed state
**Priority:** Low — Polish  
**Effort:** Low  

Blog file rows have a hover background but no `:active` pressed state. Clicking feels unresponsive.

**Fix:** Add `.blog-file:active { background: rgba(99,212,245,0.12); }`.

---

### 9. Toast notification positioning
**Priority:** Low — Polish  
**Effort:** Low  

The "Message sent" toast appears centered on screen with a scale animation. Easy to miss, especially on large screens.

**Fix:** Move to top-center with a slide-down animation. Change `top: 50%` to `top: 60px` and animate `translateY` from `-20px` to `0`.

---

### 10. Suggestion button shimmer on first load
**Priority:** Low — Polish  
**Effort:** Medium  

The suggestion buttons below the input are easy to overlook. A one-time shimmer or fade-in sequence would hint they're interactive.

**Fix:** Add a staggered `animation-delay` fade-in on `.sug-btn` when the input section becomes visible.

---

### 11. Cache buster on script.js
**Priority:** Low — DX  
**Effort:** Low  

`script.js?v=3` requires manual bumping. Cloudflare handles cache invalidation on deploy anyway.

**Fix:** Remove the `?v=3` query param, or automate it with a deploy script if needed.
