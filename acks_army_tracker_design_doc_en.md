
# Project: Army Tracking and Reconnaissance System for ACKS II

## General Overview

This is a web application for the game master (GM) running a campaign using the ACKS II system. It allows the GM to:
- Display a world map divided into hexes (24 and 6 miles),
- Manage armies and characters (location, parameters),
- Perform visibility checks based on dice rolls,
- Provide players with reconnaissance data (via login).

Technologies used: **HTML/CSS/JS** (potentially Node.js or Supabase/Firebase in the future).

---

## User Stories

### Game Master (GM)
- As a GM, I want to see the map with armies and characters so I can track their movement.
- As a GM, I want to edit army parameters (manually or from templates) to reflect in-game changes.
- As a GM, I want to perform visibility rolls between armies to determine who sees whom.
- As a GM, I want to see the results of reconnaissance rolls and make decisions accordingly.
- As a GM, I want to manage player access so they don't see hidden information.

### Player
- As a player, I want to log into the system and only see armies visible to my faction.
- As a player, I want to view the main parameters of allied armies to plan my actions.
- As a player, I want to receive updated information after each turn.

---

## Core Entities

### Hex
- ID (e.g., "F12")
- Coordinates
- Scale (24 miles / 6 miles)
- Terrain (optional)
- Attached objects (armies, settlements, characters)

### Army
- Name / ID
- Faction (e.g., Northumbrians, Picts)
- Current hex
- Size, speed
- Stealth rating (modifier to hiding)
- Fatigue (optional)
- Special properties (e.g., magical concealment)

### Character (optional)
- Name
- Attached to an army or acting independently
- Role (scout, diplomat, mage, etc.)

### Recon Data
- Army A sees Army B starting from turn X
- Visibility mechanic: 1 d20 roll with modifiers

### User
- Name / login
- Password (mocked initially, secure later)
- Role: GM / player
- Faction (e.g., "Picts")
- Visible information

---

## Key Features

| Feature                                | Required for MVP? | Notes                      |
|----------------------------------------|--------------------|----------------------------|
| Map loading with hex grid              | ✅                 | SVG or Canvas              |
| Add army to map                        | ✅                 | Initially manually          |
| Move army between hexes                | ✅                 | Simple drag or controls    |
| Edit army parameters                   | ✅                 | Simple form                |
| Perform visibility rolls               | ✅                 | Basic d20 with modifiers   |
| Store visibility info (who sees whom)  | ✅                 | With timestamps or turns   |
| User login                             | ❌                 | Later, post-MVP            |
| Limit info by player faction           | ❌                 | Important, but later       |
| Foundry VTT integration                | ❌                 | Optional                   |

---

## Development Stages

**Stage 1: MVP**
- Map, army management, movement, visibility, GM-only UI

**Stage 2: Extended Logic**
- Recon history and logs
- Enhanced detection system (range, modifiers, conditions)

**Stage 3: Multi-user Access**
- Login, roles, faction-based access

**Stage 4: Integration and Persistence**
- Data storage (localStorage → database)
- Import/export support
- Integration with Foundry or other tools
