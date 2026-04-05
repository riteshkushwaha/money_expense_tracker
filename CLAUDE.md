# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Quick Start

### Running the Application
```bash
python3 app.py
```
The app starts in debug mode on `http://localhost:5001` with hot-reload enabled.

### Installing Dependencies
```bash
pip install -r requirements.txt
```

### Running Tests
```bash
pytest
```

## Project Architecture

This is an **educational expense tracker** built with Flask, designed as a progressive learning path. Routes follow a phased approach with placeholder implementations for features students will build incrementally.

### Core Structure

**Frontend (Templates & Static)**
- All templates extend `templates/base.html` using Jinja2 block inheritance
- Use `{{ url_for('route_name') }}` for all internal links to maintain URL integrity
- CSS uses a design system with CSS custom properties (defined in `:root`)

**Backend (Routes)**
- Routes are organized in `app.py` with clear comment blocks separating sections
- Current routes: landing (`/`), auth pages (`/register`, `/login`), legal pages (`/terms`, `/privacy`)
- Placeholder routes contain "coming in Step X" messages for features in development

**Database**
- `database/db.py` is a template file students will implement
- Should contain: `get_db()`, `init_db()`, and `seed_db()` functions
- Uses SQLite with row_factory and foreign keys enabled (per comments)

### Design System

**Color Variables** (defined in `style.css `:root`)
- Primary text: `--ink` (#0f0f0f), `--ink-soft` (#2d2d2d), `--ink-muted` (#6b6b6b)
- Background: `--paper` (#f7f6f3), `--paper-warm` (#f0ede6), `--paper-card` (white)
- Accent: `--accent` (#1a472a), `--accent-light` (#e8f0eb)
- Secondary: `--accent-2` (#c17f24), `--accent-2-light` (#fdf3e3)
- Danger state: `--danger` (#c0392b), `--danger-light` (#fdecea)

**Typography**
- Display/Headings: DM Serif Display (serif)
- Body text: DM Sans with weights 300, 400, 500, 600

**Layout**
- Max width: 1200px (desktop content)
- Auth pages: 440px width
- Responsive breakpoints at 900px and 600px (check landing.html and legal pages for mobile patterns)
- Radius values: `--radius-sm` (6px), `--radius-md` (12px), `--radius-lg` (20px)

### Notable Implementation Patterns

**Modal System** (used in landing page video modal)
- Built with vanilla JavaScript (no dependencies)
- Close on button click, overlay click, or Escape key
- Video iframe has src reset on close to stop playback (prevents background audio)
- Use this pattern for future interactive overlays

**Template Inheritance**
- `base.html` provides: navbar, main content area, footer with legal links
- All new pages should extend base.html with `{% extends "base.html" %}`
- Override content with `{% block content %}...{% endblock %}`
- Add custom styles in `{% block head %}` if needed
- Add custom scripts in `{% block scripts %}` if needed

## Routes and Features

### Implemented
- `GET /` → Landing page (landing.html)
- `GET /register` → Registration form (register.html)
- `GET /login` → Login form (login.html)
- `GET /terms` → Terms and Conditions legal page
- `GET /privacy` → Privacy Policy legal page

### Placeholder Routes (to be implemented by students)
- `/logout` - Step 3
- `/profile` - Step 4
- `/expenses/add` - Step 7
- `/expenses/<id>/edit` - Step 8
- `/expenses/<id>/delete` - Step 9

When implementing placeholder routes, return proper template renders (not text placeholders).

## Common Development Tasks

### Adding a New Page
1. Create template in `templates/new_page.html` extending base.html
2. Add route in `app.py` following the existing pattern (render_template)
3. Update navigation links using `url_for('route_name')`
4. Add custom styles in the template's `{% block head %}` if needed

### Styling Consistency
- Always use CSS custom properties (from `:root`) instead of hardcoded colors
- Reference existing component styles in style.css for patterns (navbar, footer, buttons)
- Test responsive behavior at 900px and 600px breakpoints

### Adding Forms
- Check login.html and register.html for form patterns
- Forms should extend base.html
- Use semantic HTML with proper labels and input types

## Notes for Future Work

- Database integration is student-led: db.py needs implementation before auth/expense features work
- The project emphasizes learning through progressive implementation
- Keep frontend logic minimal (vanilla JS only, per project philosophy)
- All internal links should use `url_for()` to avoid broken routes if paths change
