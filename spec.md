# Markdown Pretty - Technical Specification

## 1. Project Overview

Markdown Pretty is a modern markdown editor web application with real-time preview, version history, AI-powered enhancements, and seamless sharing capabilities. The application follows a mobile-first responsive design approach.

### 1.1 Success Criteria

- Users can create, edit, and share markdown documents with minimal friction
- The editor provides a clean, intuitive interface with real-time preview
- AI assistance enhances the writing experience
- Version history provides safety and flexibility
- The application is responsive across all device sizes

## 2. Technical Architecture

### 2.1 Frontend
- **Framework**: React with TypeScript
- **Styling**: Tailwind CSS (utility-first approach)
- **Component Library**: shadcn/UI
- **State Management**: React Context API for global state, component state for local state
- **Routing**: React Router v6 with protected routes for authenticated areas

### 2.2 Backend Services
- **Database & Storage**: Supabase (https://supabase.com/docs)
  - PostgreSQL database
  - Supabase Storage for file storage
  - Row-Level Security for data protection
- **Authentication**: Clerk (https://supabase.com/partners/integrations/clerk)
  - Google OAuth provider
  - Integration with Supabase for user management
- **AI Integration**: Anthropic API
  - Server-side integration for document enhancement

### 2.3 System Architecture

The application follows a full-stack React architecture with client-side rendering. All business logic will be implemented within the React application, with Supabase serving as the data persistence layer. The application will use the Supabase JavaScript client to interact with the database and storage.

Authentication flow will use Clerk for the user-facing components with webhook integration to Supabase. All data access will be secured through Supabase Row-Level Security policies, ensuring users can only access their own data.

API communication for AI features will use secure server-side calls to the Anthropic API to prevent exposing API keys to the client.

## 3. Feature Specification

### 3.1 "Home" Page (Public)

#### Hero Section
- Title: "**Markdown editing, beautifully reimagined**" (with "beautifully" in the custom primary color #8A8ADF)
- Sub-text: "A clean, intuitive markdown editor with live preview and AI editing assistance. Create, manage, and share markdown docs, delightfully."
- Call-to-action button: "See it in action" - Links to an unauthenticated version of the Markdown editor

#### Features Showcase
- Title: "**Markdown Pretty is pretty simple**"
- Visual representations of key features:
  - Real-time preview (split panel)
  - AI Assistance
  - Easy sharing
  - Version control

### 3.2 Authentication

- **Authentication Provider**: Clerk via Supabase integration (https://supabase.com/partners/integrations/clerk)
- **Authentication Method**: Google Account sign-in only
- **Implementation Details**:
  - Configure Clerk project to support Google OAuth provider only
  - Set up Supabase-Clerk integration using webhooks to sync user data
  - Use Clerk's frontend components for sign-in/sign-up flows
  - Implement Clerk's session management for protected routes
  - Follow the integration guide: https://supabase.com/partners/integrations/clerk

### 3.3 "User Dashboard" Page (Protected)

- **Layout**: Open to developer creativity with the following guidelines:
  - Filter box for partial name matching
  - Document metadata display: Name, Created date, Edited date
  - Time-based grouping: Today, Yesterday, Previous 7 Days, Previous 30 days, Monthly (e.g., March, February, January, 2024)
  - No folders or tags required

- **Document Actions**:
  - Create new document (redirects to Markdown Editor page)
  - Rename document
  - Delete document (with confirmation)
  - Edit document (redirects to Markdown Editor page)
  - Compare versions (opens the version comparison page)
  - Share (generates shareable link with toast notification)
  - Unshare (removes public access with toast notification)

### 3.4 "Markdown Editor" Page (Protected)

#### Requirements
- Split-pane live preview
- TypeScript compatible
- GitHub markdown syntax support
- Clean, simple design similar to GitHub
- Basic toolbar required

#### Technical Considerations
- Consider libraries like "react-markdown" or "uiw/react-markdown-editor" or similar recommended libraries
- Should be stylable with Tailwind CSS
- Implement "scroll lock" feature (synchronize scrolling between editor and preview) if available in the chosen library

#### Basic Toolbar
- Implement a clean, minimal toolbar with essential markdown formatting options:
  - Headers (H1, H2, H3)
  - Bold
  - Italic
  - Lists (ordered and unordered)
  - Links
  - Code blocks
  - Scroll lock toggle (if available in the library)
- Toolbar should follow the overall design aesthetic and use Tailwind styling
- Position at top of editor pane

#### Mobile Adaptation
- On mobile devices, preview pane stacks under the editor

#### Actions
- Save document
- Save new version (creates a new version and displays "New version saved!" toast notification)
- Share document (generates public link)
- Compare versions (opens the version comparison page)

#### Document Save Flow
- **First Save**:
  - When user clicks "Save" for the first time on a new document:
    - Present a modal dialog to name the document
    - Modal includes: text input field (pre-populated with "Untitled Document"), Save button, Cancel button
    - Validate name is not empty before allowing save
    - On successful save, update the document title in the editor header and show "Document saved!" toast
  
- **Subsequent Saves**:
  - Quick save without prompting (updates existing document)
  - Show brief "Saved successfully" toast confirmation

- **Unsaved Changes Handling**:
  - Track document modified state (isDirty flag)
  - If user attempts to navigate away or close tab with unsaved changes:
    - Show browser's native "Changes you made may not be saved" confirmation
    - If using React Router, implement a prompt when navigating away from editor with unsaved changes
  - Periodically save content to localStorage as backup (optional, for recovery)

#### Sharing within Editor
- When user clicks "Share":
  - Generate a public link
  - Display modal with link and "Copy" button
  - Clicking "Copy" copies link to clipboard and shows "Link copied!" toast
  - Once shared, the Share button changes to "Unshare"
  - Clicking "Unshare" removes public access and shows "Document unshared" toast

#### AI Assistance
- "Ask AI" button in markdown editor view
- Support for manual written prompts
- "Quick prompts" options:
  - Fix my syntax
  - Restructure for clarity
  - Fix grammar and spelling
  - Write more directly and clearly
- Side-by-side comparison of original vs. AI-edited version
- Options to:
  - Save new version (full replacement)
  - Cancel (discard AI changes)

#### API Key Management
- Application provides a default Anthropic API key (accessible only to admin-selected users)
- Users can bring their own Anthropic API key
- Secure storage of API keys in backend (not exposed to frontend)
- UI to securely save/delete own Anthropic API key

### 3.5 "Compare Versions" Page (Protected)

- **Access**: Available via:
  - Action button in the dashboard
  - Action button in the document editor
  - Shortcut in document menu/toolbar

- **Layout**: 
  - 3-pane view:
    - Left: Versions list (with timestamps)
    - Middle: Selected version content
    - Right: Current version content
  - Each content pane has toggle between raw markdown and rendered HTML view
  - No difference highlighting between versions (simple side-by-side comparison)

- **Version Selection**:
  - List displays all saved versions in reverse chronological order
  - Each version shows timestamp and version number
  - Clicking a version loads it in the middle pane for comparison

- **Actions**:
  - "Restore this version" button (with confirmation dialog explaining this will delete all subsequent versions)
  - "Back to editor" button to return without making changes

- **Version Creation**:
  - Versions are created from the Editor page using the "Save new version" button
  - User-initiated version creation only (no automatic saves as versions)
  - No commit messages required
  - When saved, user sees "New version saved!" toast notification

- **Mobile Adaptation**:
  - On mobile devices, the 3 panels are stacked vertically

### 3.6 "See it in Action" Page (Public)

- **Purpose**: Allow users to experience the editor without creating an account
- **Implementation**: 
  - Uses the same Markdown Editor component as the protected page
  - All core editing functionality works (typing, formatting, preview)
  - Pre-populated with sample markdown content showcasing key features
- **Key Differences**:
  - "Sign up" button replaces the "Save" button
  - When clicked, directs user to authentication flow
  - AI assistance button is present but deactivated (grayed out)
  - No version history access
  - No document sharing functionality
- **Authentication**:
  - Uses the same authentication flow as the main application

### 3.7 "Shared Document View" Page (Public)

- **Purpose**: Allow anyone to view a shared document without requiring authentication
- **Functionality**:
  - Markdown rendered as HTML in a clean, visually appealing format
  - Document title displayed prominently
  - "Download" button to download the document as Markdown
  - "Create copy" button that requires authentication and copies the document to the user's dashboard
  - No editing capabilities
  - Clean, minimal design that focuses on content readability
  - Responsive layout that works well on all devices

## 4. Database Schema and API Endpoints

The following schema is recommended based on the requirements and Supabase integration:

### 4.1 Database Schema

#### Users Table
- id (primary key, UUID generated by Supabase)
- clerk_id (string, the user ID from Clerk for mapping between services)
- email (string)
- created_at (timestamp with time zone)
- updated_at (timestamp with time zone)
- can_use_app_api_key (boolean)

#### API Keys Table
- id (primary key)
- user_id (foreign key to Users)
- api_key (encrypted)
- created_at (timestamp with time zone)
- updated_at (timestamp with time zone)

#### Documents Table
- id (primary key)
- user_id (foreign key to Users)
- title (string)
- content (text)
- created_at (timestamp with time zone)
- updated_at (timestamp with time zone)
- is_shared (boolean)
- share_id (UUID, unique identifier for shared link)

#### Versions Table
- id (primary key)
- document_id (foreign key to Documents)
- content (text)
- created_at (timestamp with time zone)
- version_number (integer)

**Note on Auth Implementation**:
- User authentication data is primarily stored and managed in Clerk
- Supabase's `auth.users` table will be populated through the Clerk-Supabase integration
- The custom `users` table above will be used for application-specific user data
- Use Supabase Policies (Row-Level Security) to control access to data based on user authentication

### 4.2 Row-Level Security Policies

The following RLS policies should be implemented in Supabase:

#### Documents Table
```sql
-- Allow users to select only their own documents
CREATE POLICY "Users can view their own documents" 
ON documents FOR SELECT 
USING (auth.uid() = user_id);

-- Allow users to insert their own documents
CREATE POLICY "Users can create documents" 
ON documents FOR INSERT 
WITH CHECK (auth.uid() = user_id);

-- Allow users to update only their own documents
CREATE POLICY "Users can update their own documents" 
ON documents FOR UPDATE 
USING (auth.uid() = user_id);

-- Allow users to delete only their own documents
CREATE POLICY "Users can delete their own documents" 
ON documents FOR DELETE 
USING (auth.uid() = user_id);

-- Allow anyone to view shared documents
CREATE POLICY "Anyone can view shared documents" 
ON documents FOR SELECT 
USING (is_shared = true);
```

#### Versions Table
```sql
-- Allow users to view versions of documents they own
CREATE POLICY "Users can view versions of their documents" 
ON versions FOR SELECT 
USING (
  EXISTS (
    SELECT 1 FROM documents 
    WHERE documents.id = versions.document_id 
    AND documents.user_id = auth.uid()
  )
);

-- Allow users to create versions for documents they own
CREATE POLICY "Users can create versions for their documents" 
ON versions FOR INSERT 
WITH CHECK (
  EXISTS (
    SELECT 1 FROM documents 
    WHERE documents.id = versions.document_id 
    AND documents.user_id = auth.uid()
  )
);

-- Allow users to delete versions of documents they own
CREATE POLICY "Users can delete versions of their documents" 
ON versions FOR DELETE 
USING (
  EXISTS (
    SELECT 1 FROM documents 
    WHERE documents.id = versions.document_id 
    AND documents.user_id = auth.uid()
  )
);
```

#### API Keys Table
```sql
-- Allow users to view only their own API keys
CREATE POLICY "Users can view their own API keys" 
ON api_keys FOR SELECT 
USING (auth.uid() = user_id);

-- Allow users to insert their own API keys
CREATE POLICY "Users can create API keys" 
ON api_keys FOR INSERT 
WITH CHECK (auth.uid() = user_id);

-- Allow users to update only their own API keys
CREATE POLICY "Users can update their own API keys" 
ON api_keys FOR UPDATE 
USING (auth.uid() = user_id);

-- Allow users to delete only their own API keys
CREATE POLICY "Users can delete their own API keys" 
ON api_keys FOR DELETE 
USING (auth.uid() = user_id);
```

### 4.3 API Endpoints

The application will use the following Supabase API endpoints:

#### Authentication
- Sign in/Sign up via Clerk (handled by Clerk SDK)
- Verify session status

#### Documents
- `GET /documents` - Retrieve user's documents with filtering/pagination
- `GET /documents/:id` - Retrieve a specific document
- `POST /documents` - Create a new document
- `PUT /documents/:id` - Update a document
- `DELETE /documents/:id` - Delete a document
- `PUT /documents/:id/share` - Generate or revoke a shareable link
- `GET /shared/:share_id` - Retrieve a shared document by share ID

#### Versions
- `GET /documents/:id/versions` - List versions for a document
- `GET /documents/:id/versions/:version_id` - Get a specific version
- `POST /documents/:id/versions` - Create a new version
- `POST /documents/:id/versions/:version_id/restore` - Restore to a specific version

#### API Keys
- `GET /api-keys` - Get user's API key (if exists)
- `POST /api-keys` - Save user's API key
- `DELETE /api-keys` - Delete user's API key

#### AI Assistance
- `POST /ai/enhance` - Process document with AI assistance

## 5. Error Handling and Validation

### 5.1 Error Handling Approach
- Toast notifications for errors with contextual information
- Clear, user-friendly error messages
- Graceful handling of common errors:
  - Network issues
  - Authentication failures
  - API failures
  - Save failures

### 5.2 Error States and Recovery

| Error Type | UI Treatment | Recovery Strategy |
|------------|--------------|-------------------|
| Network Connectivity | Toast notification with retry option | Auto-retry with exponential backoff |
| Authentication Error | Redirect to login with message | Preserve state for when user returns |
| Save Failure | Toast with detailed error and retry | Backup to localStorage and provide manual retry |
| API Timeout | Toast notification with retry option | Retry automatically once |
| AI Service Unavailable | Disable AI features, show notice | Fallback to basic editing experience |
| Invalid Document Format | Warning with details of issues | Offer to fix common problems automatically |
| Version Conflict | Modal showing differences | Allow user to choose version or merge |

### 5.3 Data Validation Rules

#### Document Creation/Update
- Title: Required, 1-100 characters
- Content: No size limit, but UI should warn at 1MB+

#### API Key Validation
- Must match Anthropic API key format
- Must be encrypted before storage
- Validate with a simple request before saving

#### Version Management
- Prevent empty versions (no changes)
- Maximum 100 versions per document (with UI warning at 50+)

### 5.4 Client-Side Validation
- Form validation using React Hook Form or similar library
- Real-time validation feedback
- Submit buttons disabled until form is valid

### 5.5 Rate Limiting and Abuse Prevention
- Implement rate limiting on AI requests (max 10 per minute per user)
- Implement throttling on document saves (max 60 per minute per user)
- Monitor for suspicious activity patterns

## 6. Testing Strategy

### 6.1 Testing Approach

#### Unit Testing
- Test all critical functions and components
- Focus on complex business logic
- Use Jest for JavaScript/TypeScript testing
- Minimum 80% code coverage for core functionality

#### Component Testing
- Test all UI components in isolation
- Use React Testing Library for component tests
- Include accessibility testing in component tests
- Test both appearance and behavior

#### Integration Testing
- Test interactions between components
- Test data flow through the application
- Focus on key user workflows:
  - Document creation and editing
  - Version management
  - Sharing functionality
  - AI assistance

#### End-to-End Testing
- Use Cypress or Playwright for E2E tests
- Cover critical user journeys:
  - User registration and login
  - Creating, editing, and saving documents
  - Sharing documents and accessing shared documents
  - Creating and restoring versions
  - Using AI assistance features

#### API Testing
- Test all API endpoints
- Verify correct data handling
- Test error cases and edge cases
- Use Postman or similar tool for API testing

### 6.2 Security Testing

- Authentication and authorization testing
- Input validation and sanitization
- SQL injection prevention
- XSS prevention
- API key security
- CSRF protection
- Regular dependency vulnerability scans

## 7. Implementation Plan

### 7.1 Development Phases

#### Phase 1: Core Platform
1. **Setup Project Infrastructure**
   - Initialize React project with TypeScript
   - Configure Tailwind CSS
   - Set up routing with React Router
   - Create component library
   - Configure Supabase connection

2. **Header and Footer Components**
   - Create responsive header
   - Create responsive footer
   - Implement navigation logic

3. **Homepage**
   - Build homepage layout
   - Implement hero section
   - Create features showcase
   - Add "See it in action" button and functionality

4. **Authentication Integration**
   - Integrate Clerk authentication
   - Configure Supabase-Clerk integration
   - Implement protected routes
   - Create login/signup flows
   - Test authentication flows

5. **Dashboard Page (Basic)**
   - Create dashboard layout
   - Implement document listing
   - Add document grouping by date
   - Create filter functionality
   - Add basic document actions (without implementation)

#### Phase 2: Essential Document Features
6. **Document Editor**
   - Research and select markdown editor library
   - Implement split-pane editor
   - Create basic toolbar
   - Implement scroll lock (if available)
   - Create responsive layouts for desktop/mobile
   - Build document save functionality
   - Implement unsaved changes detection

7. **Document Management**
   - Complete document CRUD operations
   - Implement rename functionality
   - Implement delete functionality (with confirmation)
   - Add document metadata display
   - Create real-time saving feedback

8. **"See it in Action" Page**
   - Create unauthenticated editor experience
   - Add sample content
   - Implement authentication prompt modal
   - Link to authentication flow

#### Phase 3: Differentiation Features
9. **Document Sharing**
   - Implement public link generation
   - Create shared document view
   - Build download functionality
   - Add "Create copy" feature
   - Implement unshare functionality
   - Add security checks for shared content

10. **Version Control and Comparison**
    - Create version history storage
    - Implement "Save new version" functionality
    - Build version comparison interface
    - Create version restore functionality
    - Implement mobile-responsive version view

#### Phase 4: AI Features
11. **AI Integration with Default API**
    - Implement secure storage of app API key
    - Create AI enhancement API endpoint
    - Build UI for AI assistance
    - Implement quick prompts
    - Create side-by-side comparison view
    - Add functionality to accept/reject AI changes

12. **User API Key Management**
    - Create secure API key storage
    - Build API key management UI
    - Implement validation of user API keys
    - Add admin functionality to manage user access

### 7.2 Dependencies and Critical Path

- Authentication must be completed before document management
- Basic editor must be implemented before version control
- Version control must be completed before AI enhancement comparison
- Core document functionality must be stable before implementing sharing

### 7.3 Development and Testing Milestones

- **Milestone 1**: Core platform functional (end of Phase 1)
  - User can sign up, sign in, and view dashboard
  - Homepage complete with navigation to editor

- **Milestone 2**: Basic document functionality (end of Phase 2)
  - User can create, edit, save, rename, and delete documents
  - Editor works responsively on desktop and mobile

- **Milestone 3**: Sharing and versioning (end of Phase 3)
  - User can share documents and manage versions
  - Complete version comparison and restoration

- **Milestone 4**: AI enhancement (end of Phase 4)
  - User can use AI to enhance documents
  - User can manage their own API key

## 8. Security Considerations

### 8.1 Authentication and Authorization
- Leverage Clerk for secure authentication
- Implement proper session management
- Use authorization checks for all protected resources
- Implement HTTP-only cookies for session persistence
- Apply principle of least privilege for all operations

### 8.2 Data Protection
- Encrypt sensitive data at rest (API keys)
- Use HTTPS for all communications
- Implement proper input validation for all user inputs
- Sanitize all content displayed in the UI
- Follow secure coding practices to prevent XSS, CSRF, and injection attacks

### 8.3 API Security
- Secure API keys storage in environment variables
- Use Supabase Row Level Security (RLS) policies to restrict data access
- Implement rate limiting for API endpoints
- Validate and sanitize all API inputs
- Log security events for monitoring

### 8.4 Shared Document Security
- Generate random UUIDs for shared document links
- Implement option to unshare documents (revoke access)
- Consider implementing optional expiration dates for shared links (future enhancement)

## 9. Design Guidelines

### 9.1 Tailwind Implementation Approach
- Utility-first approach: Build interfaces by composing small, single-purpose utility classes directly in the markup to minimize custom CSS
- Mobile-first approach: Design for mobile layouts first, then progressively enhance with responsive variant utilities (`sm:`, `md:`, `lg:`, etc.) as screen size increases
- Maintain consistent spacing and typography by leveraging Tailwind's design system

### 9.2 Color Palette
- Base palette: Tailwind Stone
- Custom primary color (use sparingly): "#8A8ADF"
- Never use pure black or pure white

### 9.3 Typography
- Use Tailwind's font sizing system consistently
- Headings: Tailwind font-bold, text-2xl/3xl/4xl
- Body text: Tailwind text-base/text-sm
- Maintain readable line lengths (max-w-prose)
- Use appropriate line heights (leading-normal/leading-relaxed)

### 9.4 Component Design
- Follow shadcn/UI design patterns for consistency
- Use consistent spacing between elements
- Ensure sufficient contrast ratios for text
- Design for touch targets (min 44px for mobile)

## 10. Out of Scope
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