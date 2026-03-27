# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Expense Tracker - a React budgeting app used as a teaching project for the Claude Code course. The project intentionally contains bugs and issues to be fixed during the course.

## Development Commands

```bash
npm run dev      # Start dev server at localhost:5173
npm run build    # Production build
npm run lint     # ESLint checks
npm run preview  # Preview production build
```

## Tech Stack

- React 19 with Vite 7
- Vanilla CSS (no framework)
- ESLint with React hooks/refresh plugins
- No backend, database, or persistence (in-memory state only)

## Architecture

Single-page React application with monolithic component structure:

- `src/main.jsx` - React entry point
- `src/App.jsx` - All application logic (single component with form, filters, summary, and transaction list)
- `src/App.css` - Component styles
- `src/index.css` - Global styles

State management uses React useState hooks at the root level. Transactions are stored in-memory with sample data.

## Known Intentional Issues

1. **Amount calculation bug** - Amounts stored as strings cause string concatenation instead of numeric addition in totals
2. **Missing delete functionality** - CSS exists for `.delete-btn` but not implemented in JSX
3. **No input validation** - Form only checks for empty fields
4. **Monolithic component** - All logic in single App.jsx file
