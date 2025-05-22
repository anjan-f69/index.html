# ANJAN SHARMA Cybersecurity Portfolio

## Overview

This is a full-stack web application for a cybersecurity professional portfolio. The application uses a React frontend with shadcn/ui components and an Express backend. Data is managed using Drizzle ORM with PostgreSQL. The application follows a modern architecture with a clear separation between client and server code.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a standard client-server architecture:

1. **Frontend**: React-based SPA built with Vite and TypeScript
   - Located in `/client` directory
   - Uses shadcn/ui component library for UI elements
   - Styled with Tailwind CSS
   - Implements React Query for data fetching

2. **Backend**: Express.js server with TypeScript
   - Located in `/server` directory
   - Provides API endpoints for client communication
   - Implements middleware for logging and error handling
   - Currently has a contact form API endpoint

3. **Database**: PostgreSQL with Drizzle ORM
   - Schema defined in `/shared/schema.ts`
   - Currently implements user model
   - Has both PostgreSQL and in-memory storage options

4. **Shared Code**: Common types and utilities shared between client and server
   - Located in `/shared` directory
   - Includes database schema definitions

## Key Components

### Frontend Components

1. **Page Components**:
   - `Home.tsx`: Main landing page integrating all section components
   - `NotFound.tsx`: 404 error page

2. **Section Components**:
   - `Navbar.tsx`: Navigation bar with section links
   - `HeroSection.tsx`: Main introduction section
   - `AboutSection.tsx`: Professional biography section
   - `ProjectsSection.tsx`: Portfolio projects showcase
   - `CertificationsSection.tsx`: Professional certifications display
   - `BlogSection.tsx`: Blog posts showcase
   - `ContactSection.tsx`: Contact form with API integration
   - `Footer.tsx`: Site footer with links
   - `ParticlesBackground.tsx`: Animated background for hero section
   - `BackToTop.tsx`: Floating button to scroll to top

3. **UI Components**:
   - Extensive collection of shadcn/ui components in `/client/src/components/ui`
   - Custom theme implementation with dark mode support

4. **Hooks**:
   - `useScrollActive.tsx`: Custom hook for tracking active section during scrolling
   - `use-mobile.tsx`: Detects mobile viewport
   - `use-toast.ts`: Toast notification system

### Backend Components

1. **API Routes**:
   - `/api/contact`: Endpoint for handling contact form submissions

2. **Database Storage**:
   - `storage.ts`: Interface and implementation for data storage
   - Currently implements in-memory storage with user management

3. **Server Configuration**:
   - Express server setup with middleware
   - Vite integration for development

## Data Flow

1. **Client-Server Communication**:
   - Frontend components make API requests to backend endpoints using React Query
   - Backend processes requests and responds with JSON data
   - API responses include success/error status and relevant data

2. **Form Submissions**:
   - Contact form collects user input in the `ContactSection` component
   - Data is validated and sent to the `/api/contact` endpoint
   - Server validates the data and returns success/error response
   - Toast notifications display the result to the user

3. **Data Storage**:
   - The application is configured to use Drizzle ORM with PostgreSQL
   - Currently implements a simple user schema with username/password
   - Also provides in-memory storage for development/testing

## External Dependencies

### Frontend Dependencies

- **UI Framework**: React with TypeScript
- **Component Library**: shadcn/ui components (built on Radix UI primitives)
- **Styling**: Tailwind CSS
- **Icons**: Font Awesome, Lucide React
- **Data Fetching**: TanStack React Query
- **Form Handling**: React Hook Form with Zod validation
- **Routing**: Wouter (lightweight router)

### Backend Dependencies

- **Server**: Express.js
- **Database ORM**: Drizzle ORM
- **Database**: PostgreSQL (using Neon Database serverless connector)
- **Validation**: Zod

## Deployment Strategy

The application is configured for deployment on Replit:

1. **Development Mode**:
   - Uses `npm run dev` to start the development server
   - Vite provides hot module replacement and fast builds
   - Server and client run concurrently

2. **Production Build**:
   - `npm run build` compiles both client and server
   - Frontend assets are built with Vite
   - Server is bundled with esbuild
   - Output is placed in the `/dist` directory

3. **Production Runtime**:
   - `npm run start` runs the production build
   - Serves static assets from the built client
   - Handles API requests through Express

4. **Database Management**:
   - `npm run db:push` command to update the database schema
   - Uses Drizzle Kit for schema migrations

## Getting Started

1. Ensure the PostgreSQL database is provisioned in your Replit
2. Set the `DATABASE_URL` environment variable
3. Run `npm install` to install dependencies
4. Run `npm run db:push` to initialize the database schema
5. Run `npm run dev` to start the development server
6. Access the application at the provided URL

## Future Enhancements

1. Implement authentication system using the existing user schema
2. Add admin panel for content management
3. Expand blog functionality with database storage
4. Implement project details pages
5. Add analytics and visitor tracking