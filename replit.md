# Novatoolz - Free Online SEO & Utility Tools

## Overview
Novatoolz is a multi-page website offering over 112 client-side SEO and utility tools across 10 categories. The project aims to provide a comprehensive suite of free, browser-based tools that require no backend, login, or database, focusing on user accessibility and privacy. The business vision is to become a go-to resource for online tools, attracting a broad user base through its extensive, easy-to-use, and privacy-centric offerings.

## User Preferences
I prefer detailed explanations and iterative development. Ask before making major changes. Do not make changes to files in the `server` directory.

## System Architecture

### Frontend
The frontend is built with React and TypeScript, using Vite for bundling. Routing is handled by `wouter`, and UI components are derived from `shadcn/ui` (Radix UI primitives). Styling is managed with Tailwind CSS, supporting dark/light modes. State management primarily utilizes React hooks. Client-side PDF processing leverages `pdf-lib` and `jspdf`.

### Core Architectural Components
- **Central Tool Registry**: `client/src/lib/tools-data.ts` organizes all tools, categories, and metadata.
- **Internationalization (i18n)**: A multi-language system supporting English, Hindi, Spanish, and French, managed by `client/src/lib/i18n.tsx`.
- **Reusable Tool Page Layout**: `client/src/components/tool-page-layout.tsx` provides a standardized structure for all tool pages, including SEO schema, breadcrumbs, "How It Works," "Features," "Benefits," "FAQs," and "Related Tools" sections.
- **SEO Component**: `client/src/components/seo-head.tsx` handles dynamic SEO elements like Open Graph tags, Twitter cards, canonical URLs, and JSON-LD schema.
- **Theming**: `client/src/components/theme-provider.tsx` implements dark/light mode functionality.
- **Navigation**: A responsive sidebar (`client/src/components/app-sidebar.tsx`) and header navigation structure the site.

### Key Features
- **112+ Client-Side Tools**: Spanning 10 categories: Calculators, Text, SEO, Image, Developer, PDF, Social, Business, System, and Student.
- **Multi-Language Support**: UI translation for 4 languages; tool inputs/outputs remain untranslated.
- **Advanced Search**: Features typewriter placeholder, live dropdown filtering, and keyboard navigation.
- **PWA Support**: Includes a manifest, service worker for offline capabilities, and an install prompt.
- **Enhanced UI/UX**: Incorporates global input focus glows, result reveal animations, copy feedback pulses, button lift effects, section fade-ins, empty state animations, and a CSS-only tooltip system.
- **Result Analysis**: Integrated into several tools, providing metrics, breakdowns, and visualizations using Chart.js.
- **Global Keyboard Shortcuts**: A system for quick navigation and actions, with a floating help panel.
- **Category-Based Theming**: A CSS-only system applies unique hover colors to tools based on their category.
- **Flight Progress Loader**: A custom canvas-drawn airplane animation for loading states.

### Backend
A minimal Express server serves the Vite frontend. No API routes or database are required as all tools are client-side.

### Design Principles
- **Privacy-Centric**: No user logins, backend APIs, or databases are used for tool functionality.
- **Performance**: Client-side execution for speed and efficiency.
- **Modern UI**: Utilizes Tailwind CSS and shadcn/ui for a clean, responsive, and aesthetically pleasing interface with dark/light mode support.
- **Accessibility**: Includes ARIA roles for enhanced search and PWA features for better user experience.
- **Consistent Layout**: All tool pages adhere to a standardized layout for predictability.

## External Dependencies
- **chart.js**: For data visualization in the Result Analysis section.
- **react-chartjs-2**: React wrapper for Chart.js.
- **pdf-lib**: Client-side PDF manipulation (merge, split, rotate, password, compress, digital signature).
- **jspdf**: Client-side PDF generation.
- **jspdf-autotable**: Plugin for `jspdf` to create tables.
- **pdfjs-dist**: For PDF rendering and parsing.
- **docx**: For processing Word documents.
- **xlsx**: For processing Excel spreadsheets.
- **mammoth**: Converts .docx to HTML.