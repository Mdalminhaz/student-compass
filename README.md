# Student Compass 🧭

An AI-powered assistant that helps CUNY students navigate campus resources and discover events — across all 17 CUNY colleges, with John Jay College of Criminal Justice as the flagship experience.

Ask a question about your campus (financial aid, clubs, advising, events, deadlines...) and Student Compass retrieves live info from official campus pages and answers it for you, chat-style.

## Features

- **Ask-anything Resource Hub** — a Claude-style chat interface for campus questions, with progressive disclosure from a big central search bar into a full chat view
- **All 17 CUNY campuses** — a searchable Campus Switcher, each with its own color theme (primary/accent/tint/ink) pulled through automatically in the Resource Hub
- **Cross-campus detection** — mention another college by name in your question and the assistant knows to route/retrieve for that campus instead
- **Guest mode** — try the full chat experience with no account; nothing is saved, and you're nudged to sign up if you want to keep it
- **Accounts** — email/password auth (JWT + bcrypt) with saved resources, recent query history, and a brute-force lockout (3 failed attempts → 60s)
- **Real RAG pipeline** — Tavily (site-restricted search) → Firecrawl (scrape to Markdown) → Claude Sonnet 4.5 (answer generation)

## Tech stack

**Backend**
- FastAPI + Motor (async MongoDB driver)
- JWT auth (PyJWT) + bcrypt password hashing
- Tavily, Firecrawl, and Claude (Anthropic) for the RAG pipeline

**Frontend**
- React (Create React App via CRACO)
- Tailwind CSS + shadcn/ui (Radix primitives)
- Framer Motion for the search-bar → chat morph animation
- react-router-dom, axios, sonner (toasts)
