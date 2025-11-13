1. Big Idea

FridgeMind is an AI-powered fridge assistant that helps people

track food,

reduce waste,

and make smarter meal decisions.

Mounted on the refrigerator door, the device uses:

a camera for automatic food recognition,

a touchscreen for quantity confirmation and inventory browsing,

a microphone for meal-related voice queries, and

an RGB LED strip for system feedback.

All image recognition and inventory management run locally on the Raspberry Pi.
A remote AI API is used only for generating meal suggestions.

2. Interaction Summary

FridgeMind centers around a simple and intuitive flow designed for everyday kitchens.

2.1 Visual Input for Food Recognition

Users place food items (e.g., eggs, vegetables, fruits, packaged goods) in front of the device.
The camera automatically identifies the food type using a lightweight ONNX vision model.

2.2 Touchscreen Confirmation

After recognition, the screen displays:

detected food category

editable quantity

auto-generated “time in fridge”

Food logging relies on image input, not voice.

2.3 Voice for High-Level Meal Guidance Only

Users can ask:

“What can I cook today?”

“Show me recipes using chicken.”

“Which foods are expiring soon?”

“What ingredients should I use first?”

Voice is used only for queries and suggestions, not data entry.

2.4 AI-Generated Recipes

Using the live inventory stored locally, FridgeMind queries an AI API to generate:

meal ideas,

ingredient usage suggestions,

simple shopping add-ons.

2.5 LED Feedback System

LED colors communicate status:

🔵 Scanning

🟢 Success

🟡 Expiring soon

🔴 Recognition error

3. Design Concept

The device is designed as a minimal, friendly module for kitchen environments:

Compact vertical layout

Smooth, rounded enclosure

Magnetic mounting for fridge doors

Bright touchscreen UI with three pages:

Capture

Inventory

Recipes

LED strip integrated for ambient feedback

Designed for one-hand, quick interactions

4. Parts Needed (Beyond Class Kit)

Raspberry Pi 4 or 5

Pi Camera Module v3

6.9–7 inch touchscreen display

USB microphone

RGB LED strip (WS2812B or equivalent)

3D-printed enclosure + magnets

Power supply, wires, connectors

Optional: diffuser panel for lighting improvement

5. Timeline
Week 1 — System Architecture & Design Concept (Nov 10–17)

Goal: Define structure and interaction model

Finalize physical layout (camera, screen, mic, LED)

Create early enclosure sketches

Build UI information architecture (Capture / Inventory / Recipes)

Test camera capture + ONNX baseline

Implement simple voice queries

Set up SQLite database schema

Deliverables: sketches, wireframes, system diagram, basic recognition demo

Week 2 — 3D Modeling & Functional Integration (Nov 17–24)

Goal: Build enclosure V1 + connect core functionality

Complete CAD model

3D-print enclosure V1 and assemble hardware

Implement touchscreen UI for recognition → quantity confirmation

Train lightweight recognition model (10 categories)

Connect recognition → SQLite → Inventory view

Deliverables: enclosure V1, working UI, vision → logging pipeline

Week 3 — AI Recipe Integration & Refinement (Nov 24–Dec 1)

Goal: Add intelligence and polish design

Refine enclosure V2 (LED integration, rounding, stability)

Add recipe suggestion UI page

Connect AI API for meal generation

Add voice commands for meal queries

Implement LED state logic

Deliverables: enclosure V2, AI recipe feature, voice query system
Functional Check-Off: Dec 1

Week 4 — Integration, Testing & Demo (Dec 1–7)

Goal: Deliver stable interactive prototype

Stress-test recognition, UI, and voice

Apply surface finishing (paint, logo)

Optimize UI animations + feedback states

Record full demo video

Prepare final documentation + presentation slides

Deliverables: final prototype, demo video, presentation (Dec 8)

6. Fall-Back Plan

To ensure successful completion under any constraints:

If recognition fails:

Use touchscreen for manual category selection.

If voice recognition becomes unreliable:

Use on-screen button to request recipes.

If AI API limits occur:

Replace with simple local rule-based meal generator.

If enclosure printing fails:

Use laser-cut acrylic or cardboard housing.

7. Group Work Distribution
Member A — Hardware & Algorithms

Camera pipeline, LED control

Vision model training + deployment

Voice query integration

Database + backend logic

AI API integration

Member B — UI & Industrial Design

Exterior sketches → CAD → printing

Touchscreen UI design

Assembly + finishing

Demo video production

Documentation & presentation

8. Documentation Plan

We will produce a complete archive including:

All sketches and design iterations

CAD files and enclosure versions

UI assets and screen flows

Code repository (vision pipeline, UI, LED logic, AI interface)

Wiring diagrams

Build instructions

Demo video

Reflection write-up

Group contribution statement

Documentation will be organized so a new person could recreate the project from scratch, matching course expectations.
