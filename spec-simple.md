# Markdown Pretty
A mobile-responsive markdown editor designed for use on any device - perfect for editing on phones, tablets, or desktops.

Prioritises efficient design by leveraging **Tailwind CSS** best practices and **shadcn/ui** components. Integrates **Supabase** for database, **Clerk** for authentication, and **Anthropic** for AI-powered writing assistance.

## Functionality

### Core
- **Basic Markdown Editing**: Split-pane live preview with GitHub markdown support and document management
- **Document Sharing**: Public link generation with "download markdown"capability
- **Version Control**: Simple version control with the ability for side-by-side comparison and restoration.
- **AI Writing Assistance**: Document enhancement using **Anthropic API** with manual prompts and quick options

### Key User Journeys
Ordered by [implementation priority](#implementation-priority):
1. Authenticate (sign in from home page using Clerk components)
2. Create, edit, save ("working copy"), save new version, of markdown documents with real-time preview
3. Manage documents from dashboard page (Actions: rename, delete, edit, see versions). Filter documents by name.
3. Share documents with non-users via public links (renders in html)
4. Compare and restore previous document versions
5. Enhance content using AI-powered assistance, initiated from Editor page "Ask AI" button
6. Non-authenticated uses can use the Editor experience, sign-in required for save and AI assistance

### UI Pages
Ordered by [implementation priority](#implementation-priority)
1. "**Home**" page (public): Hero section with call-to-action linking to unauthenticated editor demo
2. "**Dashboard**" page (protected): Document listing with filtering and grouping by date
3. "**Markdown Editor**" page (protected): Split-pane editor with toolbar, document management and AI Assistance
4. "**Shared Document View**" page (public): Public view for shared documents with "Download markdown" button
5. "**Compare Versions**" page (protected): Side-by-side version comparison to previous version(s)
6. "Compare to AI re-write" page/modal (protected): Side-by-side comparison to AI re-write of document, can save a new version, or manually copy content and cancel
6. "**See it in Action**" page (public): Unauthenticated editor demo

## Design Guide
Mobile-first approach with clean, intuitive interface that prioritises content and functionality.
- **Typography**: Consistent hierarchical text sizing using **Tailwind** font system
- **Colours**: **Tailwind Stone** palette with custom primary colour `#8A8ADF`

## Design implementation
Leverage component-based architecture with utility-first CSS to maximise development speed and maintainability.

### Tailwind Implementation Approach
Always apply Tailwind best practices:
- **Utility-first approach**: Build interfaces by composing small, single-purpose utility classes directly in the markup to minimise custom CSS
- **Mobile-first design**: Design for mobile layouts first, then progressively enhance with responsive variant utilities (`sm:`, `md:`, `lg:`, etc.) as screen size increases
- **Consistent spacing and typography**: Leveraging Tailwind's default design system

### shadcn/ui Components
Provides high-quality, customisable React components that integrate perfectly with Tailwind, reducing development time.
- Use as foundational building blocks for complex UI elements
- Extend with custom **Tailwind** classes rather than overriding styles

## Tech Stack
Full-stack React app with:
- **Frontend**: **React** with **TypeScript**, **Tailwind CSS**, **shadcn/UI**
- **Database & Storage**: **Supabase** (**PostgreSQL** & Storage)
- **Authentication**: **Clerk** via **Supabase** integration
- **AI Integration**: **Anthropic API** (server-side)

## Database Schema
Core tables with key fields:

### Users Table
- **id**: Primary key (UUID)
- **clerk_id**: Clerk user identifier
- **email**: User email
- **can_use_app_api_key**: Boolean flag for API access

### API Keys Table
- **id**: Primary key
- **user_id**: Foreign key to Users
- **api_key**: Encrypted Anthropic API key

### Documents Table
- **id**: Primary key
- **user_id**: Foreign key to Users
- **title**: Document name
- **content**: Markdown content
- **is_shared**: Boolean for public access
- **share_id**: UUID for shared link

### Versions Table
- **id**: Primary key
- **document_id**: Foreign key to Documents
- **content**: Markdown content
- **version_number**: Sequential version identifier

Note: All tables include created_at/updated_at timestamps. Security implemented via Supabase Row-Level Security policies.

## Implementation Priority
1. **Core platform**: Project setup, header/footer, Home page, authentication, Dashboard page (basic) 
2. **Essential document features**: Editor, document management
3. **Advertise the app**: Demo Editor experience
4. **Differentiation features**: Sharing, version control
5. **AI features**: Anthropic integration, API key management

## Out of Scope
The following items are explicitly out of scope for the initial implementation:
- Accessibility compliance (WCAG standards)
- Advanced folder/tag organization
- Complex diff visualization
- Advanced markdown editor features beyond the basic toolbar
- Offline capabilities
- Collaborative editing

## References
- [Tailwind CSS Utility-First Documentation](https://v3.tailwindcss.com/docs/utility-first) - Official guide on Tailwind’s utility-first approach.
- [shadcn/ui Documentation](https://ui.shadcn.com/docs) - Reference for shadcn/ui components.
- [Supabase](https://supabase.com) - Platform for database, authentication, and storage.
- [Supabase and Clerk Integration](https://supabase.com/partners/integrations/clerk) - Details on integrating Clerk for authentication.