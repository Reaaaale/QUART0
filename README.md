# Real-Time Water Polo Scoreboard System

A real-time desktop system for managing official water polo matches, designed for in-venue operations and external LED wall displays. The application is built to be reliable under live-match conditions, with low-latency updates and a clear operational workflow.

## Purpose
This project provides a full match control workflow (setup ? control ? display) with live synchronization between the operator interface and the public scoreboard. The system is intended for real match environments where timing, correctness, and visibility are critical.

## Architecture
- **Backend**: Node.js WebSocket server as the single source of truth for match state.
- **Frontend**: React UI for setup and control, plus a dedicated display view optimized for LED walls.
- **Desktop shell**: Electron app that starts the backend, opens control, and drives the display window on a second screen.

## Core features
- Real-time synchronization of match state over WebSocket
- Match timer control (start/pause/reset) and period management
- Team setup with roster input and logo support
- Event handling: goals, timeouts, ejections, penalty events
- Operator control UI + spectator display UI
- Dedicated display window for LED wall

## Reliability and operations
- Deterministic server-side state: the server is authoritative, clients are stateless viewers
- Explicit command model (goal, timeout, ejection, clock control)
- Snapshot broadcasting for predictable client rendering

## Distribution
- Desktop packaging via Electron (Windows)
- Separate windows for control and display
- Offline licensing (device-bound) with signature verification

## Contact
For information, demo or licensing: alucda08@gmail.com
