# FridgeMind – Interactive Device Design Final Project

FridgeMind is an interactive smart hardware system designed to help users naturally track food storage, manage refrigerator inventory, and make better meal decisions.  
The project explores how AI-powered perception and generation can be embedded into everyday behaviors through a low-friction, device-centered interaction design.

---

## Team Members
- Xiaocheng Li  
- Haotian Xu  
- Xiang Chang  

## Course
Interactive Device Design

---

## Big Idea

FridgeMind is designed around a simple insight:  
**the best moment to understand food is when people are already interacting with it.**

Rather than asking users to manually scan items or log food through an app, FridgeMind integrates directly into the act of opening the refrigerator and placing food inside. Mounted on the refrigerator door, the device observes food placement, updates inventory automatically, and provides contextual guidance only when needed.

The system combines vision-based recognition, a touchscreen interface, ambient LED feedback, and conversational AI to create a smart assistant that feels more like a part of the refrigerator than a separate device.

At the system level, FridgeMind adopts a **hybrid framework combining locally deployed models trained with Teachable Machine and AI APIs with language models**.  
Food recognition models are trained using Teachable Machine and deployed locally on a Raspberry Pi, enabling real-time recognition and inventory logging with low latency and reliability. On top of this local perception layer, AI APIs and language models are used to reason over inventory data and generate meal suggestions. This design keeps core interactions fast and self-contained, while leveraging AI for higher-level reasoning only when appropriate.

---

## Timeline

### Week 1 – Concept Definition & System Architecture
- Identified food waste and food forgetting as core problems
- Explored kitchen interaction scenarios
- Selected the refrigerator door as the primary intervention point
- Defined system architecture and interaction roles
- Conducted early food recognition feasibility tests

### Week 2 – Hardware Setup & Core Interaction Flow
- Integrated camera, touchscreen, Raspberry Pi, LED strip, and audio components
- Implemented recognition → confirmation → inventory update loop
- Built initial UI structure and inventory logic

### Week 3 – Physical Design & AI Integration
- Designed enclosure and refined physical layout
- Integrated conversational AI for meal guidance
- Redesigned LED feedback system to support new interaction states

### Week 4 – Integration, Testing & Final Presentation
- Conducted placement and behavior testing
- Refined interaction timing and feedback
- Recorded final demo video and prepared documentation

---

## Key Interaction Design

### 1. Screen Interaction (UI)

The touchscreen serves as an **information confirmation and visualization layer**, rather than a primary control surface.

Users can:
- Confirm recognized food items
- View current inventory and freshness status
- Read AI-generated meal suggestions

The interface is intentionally minimal to reduce cognitive load and allow quick, glance-based interaction.

---

### 2. Visual Recognition (Scanning)

FridgeMind does not continuously scan the inside of the refrigerator.  
Instead, recognition is **triggered by user behavior**—specifically when food is placed in front of the device during normal fridge use.

When an item enters the camera’s field of view:
1. The locally deployed recognition model identifies the food category
2. The detected item appears on the screen
3. The user confirms the result
4. The item is added to inventory

This approach:
- Aligns with natural user behavior
- Reduces privacy concerns
- Avoids unnecessary system noise

Scanning is not treated as a task, but as a natural consequence of everyday action.

---

### 3. Conversational AI Interaction (Language Model)

FridgeMind supports **direct, open-ended user queries through voice interaction**.  
Users can ask questions such as:
- “What can I cook tonight?”
- “Which foods are expiring soon?”
- “What should I use first?”

The system responds using a **combination of spoken feedback and on-screen text**, ensuring accessibility and clarity.  
Voice interaction is used exclusively for **high-level reasoning and guidance**, not for food logging or inventory modification, which helps maintain system reliability and reduces recognition errors.

This design positions the language model as a **decision-support layer**, rather than a control mechanism.

---

### 4. LED Feedback (Ambient Interaction)

An RGB LED strip provides immediate, low-cognitive-load feedback about system state:

- **Blue (dynamic):** AI is listening
- **White (rotating):** AI is processing
- **Purple:** AI is responding
- **Green:** Food recognition successful
- **Red:** Recognition failed

The LED system allows users to understand what the device is doing without reading instructions or focusing on the screen.

---

## Model Making

The physical prototype was developed through iterative stages.

### Stage 1 – Visual Feasibility Testing
The camera was first connected directly to a computer and tested in multiple refrigerator positions.  
Teachable Machine was used to train early recognition models and validate performance under real lighting conditions.

### Stage 2 – Hardware System Assembly
After confirming visual feasibility, the Raspberry Pi, touchscreen, LED strip, speaker, and camera were integrated into a complete working system.  
The focus at this stage was functional continuity rather than visual polish.

### Stage 3 – Enclosure and Form Design
With hardware dimensions fixed, enclosure design began. The goal was to keep the device thin and unobtrusive when mounted on a refrigerator door.

Because the camera required physical depth, a **ripple-inspired form language** was used to reinterpret the protrusion.  
The camera area became a visual focal point, symbolizing the system’s primary input rather than appearing as an awkward structural necessity.

---

## Code & System Implementation

> This section will be completed separately and includes:
- Local model inference
- Inventory data logging
- Voice input handling
- AI-based recipe and guidance generation

---

## Placement Testing

FridgeMind was tested on real refrigerators as well as within a simulated fridge structure.

Testing focused on:
- Whether the device interfered with door operation
- Whether users naturally noticed or ignored the device
- Visibility of LED feedback under typical kitchen lighting
- Whether food placement triggered system responses without extra user effort

Results showed that linking system activation to the moment when users open the fridge and move food inward created an intuitive, low-friction interaction that users quickly understood.

---

## Final Video & Images

The final demo video presents FridgeMind through a complete real-world usage flow, including:
- Device placement on a refrigerator door
- Food recognition and inventory updates
- Conversational AI queries and responses
- LED-based system feedback

Supporting images document real-world scale, internal hardware configuration, and enclosure design details.

---

## Reflections on Process

The most challenging aspect of FridgeMind was not implementing individual features, but ensuring that the overall interaction felt **natural, behavior-driven, and unobtrusive**.

As a device-centered design project, this raised a key question:
> How can interaction design help users understand system input and output without demanding attention?

Through this project, our understanding of “AI + Device” design evolved.  
Effective AI does not need to be loud or constantly interactive. Instead, it should work quietly in the background—recognizing food when it is placed down, updating inventory automatically, and offering guidance only when it is useful.

If we were to restart the project, we would explore deeper automation and potentially extend the system boundary to include food purchasing decisions, allowing the device to influence not only storage behavior but longer-term consumption patterns.

---
