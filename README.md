# Moodboard App Development Summary

This document provides a brief overview of the development process for the Moodboard Generator application.

## Core Idea

The application allows users to input their aspirations or ideas, and leverages AI (specifically OpenAI's GPT-4o and DALL-E 3) to generate textual descriptions and corresponding images, which are then displayed as a visually appealing mood board.

## Key Technologies

*   **Frontend Framework**: Next.js (with React)
*   **UI Library**: Material-UI (MUI)
*   **Authentication**: Clerk (frontend-based)
*   **AI Integration**: OpenAI SDK (for GPT-4o text generation and DALL-E 3 image generation via Next.js API Routes)
*   **Animations**: AOS (Animate On Scroll)
*   **Image Export**: html2canvas

## Development Highlights

1.  **Initial Setup & Authentication**:
    *   The project was set up as a Next.js application.
    *   Clerk was integrated for user sign-in, sign-up, and session management, protecting access to core features.

2.  **AI-Powered Idea Generation**:
    *   A Next.js API route (`/api/generate-idea`) was created to handle backend logic.
    *   This route securely calls the OpenAI API (GPT-4o for text, DALL-E 3 for images) using prompts provided by the user.
    *   The frontend was built to send user inputs (multiple prompts allowed) to this API route and display the returned text and image URLs.

3.  **Mood Board UI & UX**:
    *   A custom card component (`CustomIdeaCard`) was developed to display each generated idea (image on top, text below).
    *   Cards are given a random tilt (-45 to +45 degrees) for a dynamic, "scattered" look.
    *   The main display area is styled as a "board" with user-controlled spacing between cards (via a slider).
    *   AOS library was added for fade-up animations as cards appear.
    *   The overall application features a global peach gradient background, with content areas styled using light, elevated "glassmorphism" effects.

4.  **Export Functionality**:
    *   Users can save their generated mood board as a JPEG image using the `html2canvas` library, which captures the mood board section of the page.

5.  **Code Organization & Refinement**:
    *   TypeScript interfaces were centralized into a dedicated `src/types/index.ts` file for better modularity.
    *   Build and linting issues were progressively addressed to ensure code quality and a successful production build.

This phased approach allowed for iterative development, starting with core authentication and gradually adding AI features, UI refinements, and export capabilities. 
