# Technical System Design (TSD)

Version: 1.0

---

# 1. Architecture

Application Type:

Progressive Web App (PWA)

Architecture:

Client + Local Database

Goal:

Fast, simple, maintainable, offline-friendly.

---

# 2. Technology Stack

Frontend:

* Next.js
* TypeScript
* Tailwind CSS
* shadcn/ui

Database:

* SQLite

Deployment:

* Vercel

PWA:

* next-pwa

---

# 3. Folder Structure

/app

/components

/features

/content

/database

/lib

/public

/docs

---

# 4. Core Screens

## Login Profile

Purpose:

Select player profile.

Features:

* Avatar
* Name
* Continue button

---

## Home Base

Purpose:

Main hub.

Displays:

* Cubi companion
* Current level
* XP
* Coins
* Daily streak
* Continue mission

---

## World Map

Purpose:

Navigation between worlds.

Displays:

* 8 worlds
* Locked worlds
* Progress indicators
* Relics collected

---

## Mission Screen

Purpose:

Execute educational content.

Flow:

Briefing

↓

Activities

↓

Boss

↓

Rewards

---

## Parent Dashboard

Purpose:

Show learning progress.

Displays:

* Session time
* Mastery
* Streak
* Weak areas
* Strong areas

---

# 5. Database Schema

## users

Fields:

id
name
avatar
created_at

---

## progress

Fields:

id
user_id
world_id
mission_id
completed
score
date

---

## mastery

Fields:

id
user_id
topic
mastery_score

Range:

0-100

---

## rewards

Fields:

id
user_id
xp
coins
relics
streak

---

## mission_results

Fields:

id
user_id
mission_id
question_id
correct
time_spent

---

# 6. Content System

Content is stored separately from code.

Files:

vocabulary.csv

grammar.csv

missions.csv

templates.csv

Generated into:

vocabulary.json

grammar.json

missions.json

templates.json

---

# 7. Mission Engine

Mission Structure:

Mission

→ Activity 1

→ Activity 2

→ Activity 3

→ Boss Activity

→ Rewards

Each activity is generated from templates.

---

# 8. Question Types

T01

Multiple Choice

---

T02

True / False

---

T03

Drag Missing Word

---

T04

Match Word To Image

---

T05

Match Sentence Halves

---

T06

Sort Words

---

T07

Fill The Gap

---

T08

Correct The Sentence

---

T09

Listening Challenge

Future Version

---

T30

Boss Puzzle

---

# 9. Adaptive Learning

Every grammar topic receives:

mastery_score

Range:

0-100

Update logic:

Correct answer:
+2

Incorrect answer:
-3

Minimum:
0

Maximum:
100

Mission generation:

70% current topic

30% review topic

---

# 10. Reward System

XP

Used for progression.

---

Coins

Used for cosmetics.

---

Relics

One per world.

---

Streak

Daily login counter.

---

# 11. Cubi Companion

Virtual companion.

States:

* Egg
* Baby
* Explorer
* Master Explorer
* Legend

Evolution depends on XP.

No gameplay advantage.

Visual only.

---

# 12. Accessibility

Large buttons.

Minimal typing.

Readable fonts.

Mobile-first design.

Color-blind-friendly contrasts.

---

# 13. Performance Requirements

First load:

< 3 seconds

Mission load:

< 1 second

Offline support:

Required

---

# 14. Security

No external user accounts.

No social features.

No chat.

No public profile system.

Single-family usage.

---

# 15. Future Extensions

AI explanations.

AI hints.

Voice pronunciation.

Listening activities.

Additional worlds.

Multiplayer challenges.

Teacher dashboard.

---

# End of Document

