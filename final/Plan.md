1. Big Idea

FridgeMind is an AI-powered fridge assistant designed to help people track their food, reduce waste, and make smarter meal decisions.
Mounted on the refrigerator door, the device uses a camera to automatically recognize food items, a touchscreen for confirming quantity and browsing inventory, a microphone for voice-based recipe queries, and an LED strip for visual feedback.
All food recognition and inventory management run locally on the Raspberry Pi, while an external AI API provides smart meal recommendations based on real-time inventory.

The device explores how computer vision + ambient feedback + natural language interaction can create a meaningful, everyday kitchen experience.

2. Interaction Summary

FridgeMind centers around a simple and intuitive interaction flow designed for real kitchens:

1. Visual Input for Food Recognition

Users place food items (e.g., eggs, vegetables, fruits, packaged goods) in front of the device.
The camera identifies the food type automatically, using a lightweight local vision model.

2. Touchscreen Confirmation

After recognition, the screen displays the detected food type and prompts the user to confirm or adjust the quantity.
All logging is based on image input, not voice, ensuring accuracy.

3. Voice for High-Level Meal Guidance Only

The microphone enables users to ask questions such as:

“What can I cook today?”

“Show me recipes using chicken.”

“Which foods are expiring soon?”

“What ingredients should I use first?”

Voice interaction is used only for queries, suggestions, and exploration, never for adding or removing items.

4. AI-Generated Recipes

Using the real-time inventory stored locally, FridgeMind calls a remote AI API to generate meals, shopping suggestions, or ways to use nearly-expired items.

5. Ambient LED Feedback

The RGB LED strip communicates system state:

Blue = scanning

Green = recognition success

Yellow = expiring food alert

Red = recognition error

Together, these interactions create an assistant that feels responsive, helpful, and thoughtfully integrated into everyday kitchen routines.

3. Design Concept

The physical design goal is to create a compact, friendly device that blends naturally with home refrigerators:

Vertical layout with camera at the top, screen in the center, LED strip surrounding the module

Soft, rounded geometry suitable for kitchen environments

Minimal UI structure:

Capture view

Inventory view

Recipe suggestion view

Status lighting to make scanning and feedback visible from a distance

One-hand, one-gesture operation requiring minimal user effort

A 3D-printed enclosure with magnets will allow easy mounting and daily use without modifying the fridge structure.

4. Parts Needed (Beyond Class Kit)

Raspberry Pi 4/5

Pi Camera Module v3

6.9–7 inch touchscreen

USB microphone

RGB LED strip (WS2812B or similar)

3D-printed enclosure + magnets

Wires, connectors, and power supply

Optional: small diffuse panel for improving lighting around the camera

5. Timeline (Aligned with Course Deadlines)
Week 1 — System Architecture & Design Concept (Nov 10–17)

Goal: Establish the overall structure and interaction model.

Finalize physical layout (camera + screen + mic + LED).

Create hand sketches and early enclosure concepts.

Define UI information architecture (Capture / Inventory / Recipe).

Test camera capture + initial ONNX model on Raspberry Pi.

Implement simple voice queries (“What’s inside?”).

Set up local SQLite database structure for inventory.

Deliverables:

Sketches, system diagram, UI wireframes, initial image recognition demo.

Week 2 — 3D Modeling & Functional Integration (Nov 17–24)

Goal: Build enclosure V1 and fully connect core functionality.

Complete full CAD model (mounting holes, joints, vents).

3D-print enclosure V1 and assemble hardware.

Build working touchscreen UI for capture + quantity confirmation.

Train and deploy lightweight model (10 food categories).

Connect recognition to SQLite and inventory display.

Deliverables:

Enclosure V1 assembled

Camera → recognition → touchscreen confirmation → inventory logging working

UI functioning locally as a kiosk

Week 3 — AI Recipe Integration & Visual Refinement (Nov 24–Dec 1)

Goal: Add intelligence and refine the experience.

Refine enclosure V2 (LED integration, rounded edges, stability enhancements).

Add recipe suggestion UI page and inventory-to-AI formatting logic.

Integrate AI API (OpenAI / Claude / Gemini) for meal planning.

Add voice commands for queries and meal suggestions only.

Implement LED feedback states (scan, success, error, expiring).

Deliverables:

Enclosure V2 finished

AI recipe generation working

Voice-based recipe queries implemented

Ready for Functional Check-Off (Dec 1)

Week 4 — Integration, Testing & Demo Preparation (Dec 1–Dec 7)

Goal: Deliver a stable, polished interactive prototype.

Stress-test vision + UI + voice (20+ cycles).

Apply finishing touches (sanding, color, logo).

Optimize UI animation + recognition feedback.

Record demo video showing real user interaction:
Scan → Recognition → Touchscreen Confirmation → Inventory → Voice Query → AI Recipe Suggestion

Finalize documentation and presentation slides (Dec 8).

Deliverables:

Fully functioning final prototype

Demo video

Final project presentation

6. Fall-back Plan

To guarantee a working interactive device:

If vision accuracy is low:

Replace recognition with manual food selection using touchscreen.

If voice interaction becomes unstable:

Provide on-screen buttons for recipe suggestions.

If AI API integration fails or rate-limits:

Use a simple local rule-based recipe engine.

If enclosure printing fails:

Use laser-cut acrylic or cardboard as temporary housing.

This ensures the project remains complete and fully interactive under any technical constraints.

7. Group Work Distribution
Member A – Hardware & Algorithms

Camera + LED + microphone integration

ONNX model training + deployment

Voice query system

Database + backend logic

AI API integration

Member B – UI & Industrial Design

Exterior concept design + 3D modeling + printing

Touchscreen UI (Capture / Inventory / Recipe)

Visual design system

Assembly + finishing (paint, logo)

Demo video and documentation

8. Documentation Plan

We will produce:

All sketches, CAD files, and visual iterations

Code repository (camera pipeline, UI, LED logic, AI interface)

Wiring diagrams

UI assets + component library

Build instructions for reproducibility

Final write-up and reflection

Video of a real user interacting with the device

Documentation will be organized so anyone could recreate the project from scratch, matching the instructor's requirement.
