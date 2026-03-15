Act as a senior full-stack architect and build a mobile-first web application called:

AI Story Studio

IMPORTANT DEVELOPMENT RULES

• Build a clean, modular, scalable architecture
• Do NOT implement authentication yet
• Do NOT add OAuth or login systems yet
• Avoid dummy users or junk mock data
• Focus on core features first
• The project should run locally after installation
• Use production-quality folder structure and code practices

TECH STACK

Frontend
React
TypeScript
Vite
TailwindCSS

Backend
Node.js
Express.js

Database
PostgreSQL or Supabase Postgres

AI API
Groq API for text generation

DESIGN SYSTEM

Default theme: Dark mode

Colors
Background: #0F172A (Deep Slate)
Surface: #1E293B (Slate 800)
Primary AI accent: #8B5CF6 (Vivid Violet)
Creativity accents: #F59E0B (Warm Amber)

Typography
Headings: Lexend
Body text: Inter

UI rules
• Mobile-first layout
• Fixed bottom navigation bar
• Smooth 150ms transitions
• AI thinking state uses pulsing violet glow
• Story content appears with subtle fade-in animations

NAVIGATION STRUCTURE

Bottom navigation:

Home
My Stories
Gallery
Assistant

CORE FEATURE 1 — STORY IDEA INPUT

Create a Story Generator page.

User writes a story idea in a large text area.

Example:

"A girl named Riya discovers an abandoned robot in an ancient forest."

Buttons:

Analyze Story
Generate Story

CORE FEATURE 2 — AI CHARACTER EXTRACTION

When "Analyze Story" is clicked:

Send the premise to Groq API.

Extract ONLY characters mentioned in the story.

Return structured JSON:

Characters:
Riya
Robot

The UI dynamically generates character cards.

CORE FEATURE 3 — CHARACTER BUILDER

Each detected character should show expandable optional inputs:

Backstory
Personality
Motivation
Role in story

These fields enrich the final story prompt.

All inputs remain optional.

CORE FEATURE 4 — CREATIVITY CONTROL

Add a creativity slider with 5 snap levels.

Logical
Balanced
Creative
Wild
Insane

Map internally to model temperature:

Logical → 0.2
Balanced → 0.5
Creative → 0.7
Wild → 0.9
Insane → 1.1

Slider uses amber accent styling.

CORE FEATURE 5 — STORY GENERATION

When "Generate Story" is clicked:

Build a structured prompt containing:

Story premise
Character list
Character backstories
Personality traits
Motivations
Tone
Creativity level

Send to Groq API.

Output requirements:

• Clean formatted text
• No markdown symbols
• No asterisks
• Proper paragraphs
• Narrative storytelling structure

Store generated story as Part 1.

CORE FEATURE 6 — STORY CONTINUATION

Stories must support chapters.

Structure:

Story
Part 1
Part 2
Part 3

When generating a new part:

Fetch previous parts from database and include them as context.

Generate the next chapter.

Append it to the story thread.

CORE FEATURE 7 — STORY LIBRARY

Create a "My Stories" page.

Display stories as cards:

Title
Preview snippet
Creation date

Actions:

Open
Continue Story
Delete

CORE FEATURE 8 — STORY READER

Create a clean reading interface.

Book-style layout.

Requirements:

Line height 1.6
Comfortable margins
Sequential display of story parts

Show a "Continue Story" button at the end.

CORE FEATURE 9 — STORY GALLERY

Create a browsable gallery page.

Card layout showing:

Title
Preview text
Read button

Optional sorting options:

Most recent
Longest stories
Most creative

CORE FEATURE 10 — AI STORY ASSISTANT

Create a chat interface.

Capabilities:

Suggest plot twists
Rewrite scenes
Improve dialogue
Expand chapters
Help with writing

Add quick action buttons:

Suggest Plot Twist
Expand Chapter
Improve Dialogue
Fix Grammar

Store chat history in the database.

Assistant can optionally reference a specific story.

CORE FEATURE 11 — MULTI-LANGUAGE SUPPORT

Stories should be generated in the same language as the user's prompt.

Do not restrict language.

Prompt rule:

"Generate the story in the same language used in the user’s input."

CORE FEATURE 12 — DATABASE SCHEMA

Tables:

stories
id
title
premise
tone
creativity_level
language
created_at
updated_at

story_parts
id
story_id
part_number
content
created_at

characters
id
story_id
name
backstory
personality
motivation
role_in_story

chat_history
id
story_id (nullable)
role
content
created_at

CORE FEATURE 13 — PROJECT STRUCTURE

frontend
/components
/pages
/hooks
/services

backend
/controllers
/routes
/services
/database

OUTPUT REQUIREMENTS

Before generating code:

1. Produce the full implementation plan.
2. Show database schema.
3. Show API routes.
4. Show folder structure.

Then generate the application.
