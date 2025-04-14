Ask me one question at a time so we can develop a thorough, step-by-step spec for this idea. Each question should build on my previous answers, and our end goal is to have a detailed specification I can hand off to a developer. Let’s do this iteratively and dig into every relevant detail. Remember, only one question at a time.

Here’s the idea:

```
# Markdown Pretty
A mobile-responsive markdown editor designed for use on any device - perfect for editing on phones, tablets, or desktops.

Prioritises efficient design by leveraging **Tailwind CSS** best practices and **shadcn/ui** components. Integrates **Supabase** for database, **Clerk** for authentication, and **Anthropic** for AI-powered writing assistance.

## Functionality

### Core
- **Basic Markdown Editing**: Split-pane live preview with GitHub markdown support and document management
- **Document Sharing**: Public link generation with "download markdown"capability
- **Version Control**: User-initiated versioning with side-by-side comparison and restoration
- **AI Assistance**: Document enhancement using **Anthropic API** with manual prompts and quick options

### Key User Journeys
Ordered by [implementation priority](#implementation-priority):
1. Authenticate (sign in from home page using Clerk components)
2. Create, edit, and save markdown documents with real-time preview
3. Share documents with non-users via public links (renders in html)
4. Compare and restore previous document versions
5. Enhance content using AI-powered assistance
6. Non-authenticated uses can use the Editor experience, sign-in required for save and AI assistance

## Tech Stack
Full-stack React app with:
- **Frontend**: **React** with **TypeScript**, **Tailwind CSS**, **shadcn/UI**
- **Database & Storage**: **Supabase** (**PostgreSQL** & Storage)
- **Authentication**: **Clerk** via **Supabase** integration
- **AI Integration**: **Anthropic API** (server-side)
```