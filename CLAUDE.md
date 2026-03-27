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

Single-page React application with component-based structure:

- `src/main.jsx` - React entry point
- `src/App.jsx` - Root component, manages transactions state
- `src/Summary.jsx` - Displays income, expenses, and balance (calculates totals from transactions prop)
- `src/TransactionForm.jsx` - Form for adding new transactions (manages form state, calls onAddTransaction callback)
- `src/TransactionList.jsx` - Displays filtered transaction table (manages filter state internally)
- `src/App.css` - Component styles
- `src/index.css` - Global styles

State management: App.jsx owns transactions array and passes it down. Child components manage their own local state (form inputs, filters).

## Known Intentional Issues

1. **Missing delete functionality** - CSS exists for `.delete-btn` but not implemented in JSX
2. **No input validation** - Form only checks for empty fields
