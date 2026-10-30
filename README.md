# 🚵 Whos Riding Planner (WRP)

## Project Overview
The Whos Riding Planner (WRP) is a cross-platform mobile application designed to revolutionize how friends and groups organize, track, and communicate about dirt bike rides, or any outdoor adventure requiring group coordination. It functions as a dedicated "Digital Server" for a friend's circle, centralizing chat, calendar, and map data in one place.

**Goal:** To provide a seamless, unified experience that allows groups to plan logistics, communicate instantly, and share trip memories without juggling multiple apps (texting, calendar invites, Google Maps).

## 🗺️ Core User Experience Flow (The "Discord Shell")
When a user opens the app, they should see a structure similar to Discord/Slack:
1. **Server List Panel (Left Sidebar):** Lists all groups (e.g., "Mud Run Crew," "Trail Blazers"). Tapping one selects that group.
2. **Channel List Panel (Middle Sidebar):** Once a server is selected, this lists the communication channels within that group (e.g., `#general-chat`, `#calendar-events`, `#trail-maps`).
3. **Content Panel (Right Main Area):** The main display area changes based on which channel is active:
    *   If **`#general-chat`** is selected $\rightarrow$ Shows the real-time message feed.
    *   If **`#calendar-events`** is selected $\rightarrow$ Shows the monthly calendar view and upcoming event list.
    *   If **`#trail-maps`** is selected $\rightarrow$ Displays a map of the area with marked routes and pins.

## ⚙️ Technical Architecture & Stack

| Layer | Technology / Service | Purpose | Rationale |
| :--- | :--- | :--- | :--- |
| **Client (Frontend)** | React Native / Expo | The user interface and logic that runs on the phone. | Fastest way to achieve cross-platform compatibility for a complex UI shell. |
| **Backend (Database/Auth)** | Firebase Firestore & Auth | Stores all persistent data: User profiles, Group details, Chat messages, Event records. | Provides real-time syncing capability out of the box, eliminating the need for a custom server backend. |
| **Location Services** | @expo/location | Retrieves and tracks GPS coordinates for ride planning and map pins. | Simple, robust access to native location APIs from Expo. |
| **Native UI Structure** | Custom 3-Panel Flexbox Layout | Replicates the multi-panel server experience (Discord shell). | Bypasses basic tab navigation for a richer UX tailored to the use case. |

## ✨ Feature Roadmap & Phasing

We will build this in three distinct phases to ensure minimum viable product delivery and constant testing.

### Phase 1: MVP - Core Group Planning
**Focus:** Establishing the group structure, user authentication, and basic calendar events.
*   User Registration/Login (Phone Number Auth).
*   Group Creation & Management.
*   Calendar View: Scheduling an event (date, time, location) within a specific group.

### Phase 2: Real-Time Communication
**Focus:** Building the interactive chat experience.
*   Dedicated Chat Screen implementation.
*   Sending and receiving messages in real-time using Firestore listeners.
*   Basic Group member list display.

### Phase 3: Advanced Logistics & Polish
**Focus:** Making the app truly useful for planning actual rides.
*   Map View Integration: Displaying event locations, allowing users to drop pins/draw routes on the map (using `react-native-maps`).
*   Event Details Schema: Storing specific trail details (difficulty, required gear) linked to a calendar entry.
*   Notifications: Setting up local push notifications for upcoming rides.`

---
# 🛠️ Development Workflow & Version Control
This project will adhere to best-in-class Git practices. Every major milestone, feature implementation, and bug fix will be treated as a formal development sprint culminating in a structured GitHub Commit message.

**Commit Structure Guidelines:**
*   **Feature Implementation (FEAT):** For completing entire functional units (e.g., FEAT: Implemented Phone Number Auth flow).
*   **Bug Fixes (FIX):** For resolving specific technical issues or bugs (e.g., FIX: Resolved crash when accessing map view on iOS 17).
*   **Refactoring/Polish (REFACTOR):** For improving code quality, performance, or changing the UI structure without changing visible functionality.

We will treat this `README.md` as our living project manifest, updating it with each major milestone achieved and committed to the main branch.
