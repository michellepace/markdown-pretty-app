# The Vision

### What is the name of your product or idea?
Markdown Pretty

### What problem are you solving? (500)
Writing markdown is often frustrating with editors that lack real-time preview, especially on mobile devices. Most markdown tools don't offer version history with easy restore capabilities. Sharing finished markdown documents typically requires extra steps or conversions. AI assistance for improving content is rarely integrated, and when available, doesn't allow users to bring their own API keys. Current solutions are either too basic or overwhelmingly complex.

### What's your solution in one sentence? (150)
A clean, intuitive markdown editor with live preview, version history, AI editing assistance, and 1-click public sharing capability in rendered html.

### Who is this for, describe your ideal user? (400)
Anyone who regularly works with markdown and wants a beautiful experience on any device. Our ideal user values clean interfaces, wants the power of markdown without the complexity, appreciates having version safety, and occasionally needs help optimising their writing. They want to easily share their content with a public link without any friction.

### What makes this idea different or special? (400)
Markdown Pretty combines simplicity with powerful features like AI writing assistance and unique option to use your own API key. The version history provides easy compare and restore without the complexity, while the real-time preview eliminates the edit-preview cycle. The clean, responsive design makes it accessible anywhere, and the seamless sharing feature is a beautifully rendered pleasure.

# User Journey & Experience

### What is the main thing users should be able to do? (<= 150)
Create, edit, manage, and share markdown documents. Later releases will add version history and AI writing assistance capabilities.

### Describe the key steps your user will take? (<= 600)
1. User discovers Markdown Pretty and either:
   - Signs in from homepage, lands on dashboard with a sample document
   - Tries "See it in action" demo, clicks "Sign up"
   - Google authentication
2. User creates a new document from the dashboard
3. In the split-pane editor, user writes content with live preview
4. First save creates v1 with auto-generated name (editable)
5. User enhances writing with AI assistance
6. User saves again (version 2)
7. User can compare and restores previous versions
8. User shares doc with public link
9. Returns to dashboard to manage documents

### What pages or screens will your product have? (<= 600)
1. Home Page: Hero section, features showcase, and call-to-action
2. "See it in Action" Demo Page: Functional editor without save capability
3. Authentication Page: Google sign-in via Clerk

Protected Pages:
4. User Dashboard: Document listing with filtering and time-based grouping
5. Markdown Editor: Split-pane interface with toolbar and live preview
6. AI Assistance (modal): For enhancing document content with side-by-side comparison
7. Version Comparison: 3-pane view showing version history and differences

8. Shared Document View (Public): Clean rendered view of shared documents

### What should happen after they sign up? (<= 500)
User land on their dashboard showing a sample document that introduces key features. Dashboard displays a prominent "Create New Document" button and organises documents by time-grouped layout (recency). Documents can be filtered by partial match, and actions performed (e.g., edit, delete, rename, share/unshare). Users can create a new document. In the editor, tooltips show live preview, version control, and sharing features. The AI assistance button appears with a "coming soon" hover state.

# Features & Functionality

### List the 3 most important features for launch (MVP)? (<= 600)
1. Split-Pane Markdown Editor with split-pane Live Preview: Panes stack vertically on mobiles. Includes basic formatting toolbar. Documents are automatically named on first save (with option to edit name).

2. Basic Document Management: Create, edit, save, rename, and delete. Documents organised by time-grouped layout (recency). Search bar (partial match)

3. One-Click Public Sharing: Users can generate a public link that renders their markdown as beautiful HTML. Shared documents include a "Download as Markdown" option for visitors to save content locally.

### What are some features you'd like to add later (V2 or Premium)? (<= 600)
1. Version History & Comparison: Allow users to save specific versions of documents and compare them in a side-by-side view. Users can restore previous versions when needed.

2. AI Writing Assistance: Integrate Anthropic API for document enhancement with both built-in quick prompts and custom prompts allowing a side-by-side comparison with current version. 

3. Bring Your Own LLM API Key: Users can opt to add their own Anthropic API key. This is stored securely. They are able to manage keys via their User Settings.

4. "Create Copy" Button for Shared Documents into own account

### Will users need to log in or have accounts? (<= 150)
Yes. Users must create accounts using Google OAuth sign-in via Clerk authentication to create and save documents, and access core features.

### Will users create or store any data? What kind? (<= 400)
Yes, users create and store markdown documents (text field in Documents Table). 

Suggested schema (use row level security to secure user data): 
- Users Table: clerk_id, can_use_app_api_key (boolean)
- Documents Table: id, user_id, name, content (text), is_shared, share_id (UUID)
- Versions Table: id, document_id, content (text), version_number
- API Keys Table: id, user_id, api_key (encrypted)

### Will users interact with each other? If yes, how? (<= 400)
No - users do not interact with each other. 

Users are able to share their documents with public links but there is NO collaborative editing. Documents can be downloaded only by public link viewers.

# Data & APIs

### Do you need any 3rd-party integrations or APIs? (<= 400)
Yes.
1. Clerk: for authentication with Google account (only). Clerk components will be used in the UI too enabling users to manage their profile.
2. Anthropic API: integration for AI assistance

IMPORTANT:
- See section "Features & Functionality" question "Will users create or store any data?" for suggested Database schema. This includes clerk_id and Anthropic API key.

### Will you need real-time updates or notifications? (<= 150)
Yes. Toasts for user actions, warnings, app errors. Also, we need to update the AI assistant modal with model response.

# Business Model

### How will this product make money? (<= 400)
It's free.

### Is there a target launch date or event tied to this? (<= 150)
No. For planning, use logical discrete and independent steps (without time frames).

# Branding and UI Visuals

### Provide me with your branding details, tag lines, colour theme, or colour palette, and tell me what you want your UI to look like. What brands inspire you? (<= 800)

Tagline:
- "Markdown editing, beautifully reimagined"

Colour Palette:
- Tailwind Stone with light/dark modes, avoiding pure white backgrounds and black text for reduced eye strain.
- We rely on the Stone palette's subtle variations for visual hierarchy rather than accent colours.

Typography:
- Inter for UI and rendered content, monospace font for editor. 
- We emphasise powerful typography with generous spacing as core design elements.

UI Inspiration: 
- Our content-focused approach is inspired by iA Writer's distraction-free simplicity.
- We appreciate Anthropic's friendly, approachable UI feel.

Key Elements:
- Split-pane editor/preview (stacks on smaller screens)
- For authenticated pages, we use a responsive sidebar (like for authenticated users on https://claude.ai/)