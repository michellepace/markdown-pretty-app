# Powerful Prompting Words for v0.dev

## Table of Contents
- [Words from v0 Interview Transcript](#words-from-v0-interview-transcript)
  - [Design Specification Terms](#design-specification-terms)
  - [Layout Instructions](#layout-instructions)
  - [Component Architecture Terms](#component-architecture-terms)
  - [Technical Specificity Terms](#technical-specificity-terms)
  - [Responsive Design Terms](#responsive-design-terms)
  - [Prompt Examples](#prompt-examples)
- [UIUX Designer Words](#uiux-designer-words)
- [Tailwind Words](#tailwind-words)
- [Shadcn Words](#shadcn-words)
- [More Prompt Examples](#more-prompt-examples)

⌘

## Words from v0 Interview Transcript

---

The YouTube interview with v0.dev's VP of Product showcases several categories of powerful prompting terminology that dramatically enhance v0.dev outputs. These expert phrases demonstrate technical precision, design sensibility, and clear vision—essential qualities for getting AI tools to generate exactly what you want. 

The original interview: https://youtu.be/sCFS_U7d9Do

### Design Specification Terms
- `Warmer grays` - Specifying colour temperature shows design awareness and produces more aesthetically pleasing results
- `Tighter information density` - Communicates layout priorities without needing to specify exact pixel measurements
- `Tabular-nums` - Technical CSS property knowledge that solves specific visualization problems (vertically aligned numbers)
- `Less vertical spacing` - Direct instruction about spacing that improves readability
- `Darker than original but not full black` - Nuanced colour instruction showing understanding of contrast principles

### Layout Instructions
- `Column versus under` - Clear positional language that specifies exact layout relationships
- `Aligned with` - Precise alignment language that enforces visual hierarchy
- `Make the width smaller` - Simple dimensional instruction that affects overall composition

### Component Architecture Terms
- `Break out into components` - Shows understanding of React architecture and modular design
- `Add logic to it` - Transitions from static design to functional components

### Technical Specificity Terms
- `Inter font from Google fonts with next font` - Extremely specific typography instruction with implementation method
- `Size four` - Direct reference to Tailwind's sizing system
- `Placeholder image/data` - Request for realistic mockup content

### Responsive Design Terms
- `Mobile responsive` - Triggers responsive design patterns without needing to specify breakpoints
- `Fix [specific mobile issue]` - Problem-solving approach to responsive design

### Prompt Examples

---

```
Create a dashboard with warmer grays and tabular-nums for the financial metrics. Use a tighter information density in the main table, with Less vertical spacing between rows. Make it mobile responsive.
```
This prompt combines colour temperature preferences with specific CSS knowledge and layout instructions, resulting in a more professional financial interface with proper number alignment.

```
Generate a product page with the product image aligned with the description in a column versus under it. Use Inter font from Google fonts with next font. Make the width of the description column smaller.
```
This example demonstrates precise layout positioning with specific typography requirements that would otherwise require multiple iterations to achieve.

```
Design a music player similar to Spotify but break out into components for the player controls, playlist view, and now playing section. Add logic to it that updates the now playing information when a track is selected.
```
This prompt shows understanding of component architecture and requests functional logic, taking the output beyond static design into interactive prototype territory.

```
Build an analytics dashboard with electronic music placeholder data. Make the default value of the search input 'electronic'. Adjust the colour scheme to be darker than the original but not full black, and use size four for all icon elements.
```
This example combines realistic data requests with specific Tailwind sizing instructions and nuanced colour direction, resulting in a more refined and usable interface.

## UIUX Designer Words

---

When prompting AI tools like v0.dev, using professional UIUX terminology can dramatically improve results. Here are 14 powerful words that communicate design intent clearly:

### Visual Design Principles

1. `Visual hierarchy` - Directs attention flow through deliberate sizing, contrast, and positioning (e.g., "Make the pricing tier cards use a z-20 shadow for the recommended option and z-10 for others to establish clearer visual hierarchy")
2. `Content hierarchy` - Information importance signaling (e.g., "Create clear content hierarchy with text-2xl font-semibold for primary headings, text-lg font-medium for subheadings, and text-sm text-gray-600 for supporting text")
3. `Negative space` - Strategic whitespace that improves focus and readability (e.g., "Add p-6 negative space around cards and increase to p-8 for the featured card")
4. `Card elevation` - Visual prominence through shadows and positioning (e.g., "Use three levels of card elevation: shadow-sm for inactive items, shadow-md for standard cards, and shadow-lg with a -translate-y-1 for featured elements")
5. `Gestalt principles` - Visual perception laws for unified design (e.g., "Apply the Gestalt principle of proximity by grouping related actions within a space-y-1 container and separating sections with a my-6 divider")
6. `Skeuomorphism vs. flat design` - Interface styling approach (e.g., "Add subtle skeuomorphic effects with shadow-md and a 1px border-slate-200 on cards while maintaining the overall flat design aesthetic")

### Accessibility & Usability

7. `Accessibility contrast` - WCAG compliance for text visibility (e.g., "Use text-slate-900 on white backgrounds to ensure AAA accessibility contrast ratio of at least 7:1 for all body text")
8. `Affordance` - Visual cues indicating interactivity (e.g., "Increase button affordance with hover:scale-105 transition effects and an interactive shadow-sm hover:shadow-md")
9. `Interaction parity` - Consistent behavior across devices (e.g., "Ensure interaction parity by making hover:bg-slate-100 states have equivalent focus-visible:bg-slate-100 and active:bg-slate-200 states for keyboard/touch users")

### Information & Interaction Design

10. `Information architecture` - Structured content organization (e.g., "Improve the dashboard's information architecture by using a grid-cols-12 layout with col-span-8 for primary content and col-span-4 for secondary information")
11. `Progressive disclosure` - Revealing information gradually (e.g., "Implement progressive disclosure for advanced settings using a Disclosure component from shadcn with a chevron animation on toggle")
12. `Micro interactions` - State-based animations providing feedback (e.g., "Add micro interactions using group-hover:translate-x-1 transition-all duration-200 to the chevron icon in the dropdown menu")

### Cognitive UX Principles

13. `Cognitive load` - Mental effort required for interface use (e.g., "Reduce cognitive load in checkout by limiting form fields to max 4 per step and using shadcn/Form with built-in validation")
14. `Decision fatigue` - Limited user decision capacity (e.g., "Combat decision fatigue by using a bg-primary highlight for the recommended plan and limiting feature comparison to only 5 key differences")

## Tailwind Words

---

Leveraging Tailwind-specific terminology in your prompts signals technical knowledge and produces more accurate results. Here are 14 powerful Tailwind terms:

### Core Tailwind Concepts

1. `Utility-first` - Core Tailwind approach using atomic classes (e.g., "Create a utility-first navbar with flex justify-between items-center py-4 px-6 bg-white shadow-sm")
2. `JIT compiler` - Just-in-time dynamic class generation (e.g., "Leverage dynamic classes enabled by the JIT compiler like hover:translate-y-[2px] and bg-[#3b82f680]")
3. `Arbitrary values` - Custom non-standard measurements (e.g., "Apply precise spacing with arbitrary values like pt-[72px] w-[37.5rem] and grid-cols-[1fr_2.5fr_1fr]")
4. `Custom colour palette` - Extended theme colors (e.g., "Apply our brand palette using custom colors text-brand-900 bg-brand-100 border-brand-300 where brand-900 is #0f172a")

### Layout & Responsiveness

5. `Responsive variants` - Breakpoint-specific styling (e.g., "Use responsive variants: flex-col items-start gap-4 on mobile, sm:flex-row sm:items-center sm:gap-6 on tablet, and md:justify-between on desktop")
6. `Container queries` - Component-specific responsive styling (e.g., "@container queries for a product card that's w-full @container(min-width: 300px):grid @container(min-width: 400px):grid-cols-2")
7. `Space-between` - Flexbox distribution (e.g., "Use flex justify-between items-center for the header with mr-auto on the logo and gap-4 between navigation items")
8. `Responsive typography` - Screen-adaptive text sizing (e.g., "Use text-xl lg:text-2xl xl:text-4xl font-bold for the hero heading and text-sm md:text-base text-gray-600 for the description")
9. `Spacing scale consistency` - Harmonious proportional spacing (e.g., "Maintain spacing consistency using p-4 gap-2 for small components, p-6 gap-4 for medium components, and p-8 gap-6 for large components")

### Interactive States

10. `Dark mode` - Light/dark theming (e.g., "Implement dark mode with bg-white dark:bg-slate-900 text-slate-900 dark:text-white and transition-colors duration-200")
11. `Group-hover` - Parent-trigger state changes (e.g., "Create card with group hover effects: group hover:bg-slate-50 applied to the card and invisible group-hover:visible group-hover:opacity-100 on child buttons")
12. `Ring utilities` - Focus state visualization (e.g., "Add accessible focus states with ring-2 ring-offset-2 ring-blue-500 focus:outline-none focus-visible:ring on interactive elements")
13. `Multi-variant states` - Combined interactive states (e.g., "Apply hover:bg-blue-600 active:bg-blue-700 focus:ring-2 disabled:opacity-50 disabled:bg-gray-300 disabled:cursor-not-allowed to the submit button")
14. `Pseudo-element styling` - Using before/after elements (e.g., "Add decorative elements with before:absolute before:top-0 before:left-0 before:w-full before:h-1 before:bg-gradient-to-r before:from-blue-500 before:to-purple-500")

## Shadcn Words

---

For interfaces using shadcn components, these 14 terms communicate component implementation expertise:

### Core Component Architecture

1. `Radix primitives` - Accessibility-first unstyled components that shadcn builds upon (e.g., "Implement a Select component using Radix primitives with proper aria-label attributes and keyboard navigation support with a max-h-[300px] scrollable dropdown")
2. `Compound components` - Related component pieces that share state (e.g., "Create a Form compound component with FormField, FormItem, FormLabel, FormControl, FormDescription, and FormMessage subcomponents that handle validation state together")
3. `Polymorphic components` - Components that can render as different HTML elements (e.g., "Make the Button component polymorphic using the asChild prop so it can wrap a NextLink component while maintaining all button styling")

### Navigation & Command Interfaces

4. `Command palette` - Keyboard-accessible search interface (e.g., "Add a Command palette with cmdk integration that filters through page sections and supports both keyboard shortcuts (⌘K) and click activation")
5. `Drawer navigation` - Side-sliding panel UI pattern (e.g., "Create a Drawer navigation using shadcn that slides from the left on small screens with a backdrop blur-sm effect and preserves scroll position when closed") 
6. `Sheet component` - Side panel with various anchor positions (e.g., "Create a Sheet component that slides in from the right side with size='sm' on mobile and 'default' on desktop, containing user notification preferences")

### Content Organization Components

7. `Accordion pattern` - Expandable content sections (e.g., "Use an Accordion with collapsible={false} type='single' to ensure one section always remains open, and customize the ChevronDown icon animation duration to 150ms")
8. `Collapsible sections` - Toggle visibility content areas (e.g., "Build FAQ items using Collapsible components with a custom CollapseButton that includes both a plus/minus icon transition and text color change on expanded state")
9. `Tabs with content` - Organized sectioned interface (e.g., "Build a TabsList with defaultValue='overview' and three Tab panels using underlined variant that dynamically swaps content without page reload")

### Interactive Overlay Components

10. `Context menu` - Right-click action interface (e.g., "Implement a Context menu with submenus for file actions that includes icons from lucide-react and keyboard shortcuts displayed right-aligned in text-muted-foreground")
11. `Dialogue modals` - Focus-trapping overlay components (e.g., "Use a Dialogue modal with a 3-step onboarding flow that uses Dialogue.Title with text-2xl and Dialogue.Description with text-muted, ensuring each step has a clear primary action button")
12. `Toast notifications` - Temporary feedback messages (e.g., "Show Toast notifications using useToast() hook with variant='destructive' for errors and duration={3000} for success messages, positioned in the bottom-right corner")
13. `Hover Card` - Rich preview popover for elements (e.g., "Add HoverCard components to user avatars showing detailed profile info with a 300ms openDelay and a subtle shadow-md border rounded-xl")

### Advanced Selection Components

14. `Combobox with filtering` - Searchable dropdown selection (e.g., "Implement a Combobox component that filters countries as you type with support for keyboard navigation and custom rendering of flag icons next to each option")

## More Prompt Examples

---

These prompts demonstrate how to effectively refine and enhance an existing prototype using powerful terminology that communicates design intent clearly.

### 1. Refining Visual Hierarchy

```
Adjust the dashboard's **visual hierarchy** by making the KPI cards more prominent with **ring utilities** for focus states. Apply **warmer grays** to the sidebar and implement **progressive disclosure** for the advanced filters section.
```

This prompt combines UIUX principles with Tailwind-specific terminology to refine attention flow and component relationships within an existing dashboard.

### 2. Enhancing Mobile Responsiveness

```
Make the product listing **mobile responsive** with **responsive variants** for the filters: hidden on mobile with a **drawer navigation** toggle, visible as sidebar on md: breakpoints. Increase **negative space** between product cards on smaller screens.
```

This prompt addresses device adaptability using specific Tailwind breakpoint knowledge and shadcn component patterns to optimize for mobile.

### 3. Improving Component Architecture

```
**Break out** the checkout flow into separate **compound components** for shipping, billing, and confirmation. Add **microinteractions** when moving between steps and implement **toast notifications** for form validation feedback to **reduce cognitive load**.
```

This refinement request combines component structure improvements with interaction feedback enhancements.

### 4. Adjusting Colour and Typography

```
Replace the current palette with **slate-800** for text, **emerald-500** for primary actions, and ensure **AAA accessibility contrast**. Use **tabular-nums** for the pricing tables and switch the body font to **Inter** from Google fonts with **next font**.
```

This prompt demonstrates how to precisely adjust the colour scheme and typography of an existing design with technical specificity.

### 5. Enhancing Interaction States

```
Add **group-hover** effects to the team member cards so additional contact options appear on hover. Implement subtle **microinteractions** using **JIT compiler** features for button state transitions. Ensure all interactive elements have proper **affordance**.
```

This refinement focuses on making interaction states more intuitive and engaging through specific Tailwind features.

### 6. Optimizing Information Architecture

```
Reorganize the **information architecture** of the settings page using an **accordion pattern** for related options. Create a **command palette** for quick navigation and add a **context menu** for bulk actions on list items. Aim for **tighter information density**.
```

This prompt addresses content organization and navigation patterns to improve usability of a complex interface.

### 7. Implementing State Management

```
The form needs better state handling - **add logic** to dynamically show field errors using **toast notifications**. Make the submit button use **polymorphic components** to transform into a loading state, and implement **progressive disclosure** for optional fields.
```

This prompt combines functional logic requests with UI pattern implementation to enhance form usability.

### 8. Layout Refinement

```
Adjust the blog layout to have the featured image **aligned with** the headline in a **column versus under** it. Use **space-between** for the metadata items and apply **less vertical spacing** between paragraphs. Make the width of the content column **smaller** on xl: screens.
```

This prompt uses precise layout terminology to refine content presentation and readability.

### 9. Dark Mode Implementation

```
Add **dark mode** support with appropriate colour shifts: deep **slate-800** backgrounds, **emerald-400** for accents. Ensure **AAA accessibility contrast** is maintained in both modes. Use CSS **container queries** for the sidebar to adjust its appearance based on available width rather than viewport.
```

This enhancement request focuses on theme implementation with proper colour theory and advanced responsive techniques.

### 10. Conversion Optimization

```
Reduce **decision fatigue** in the pricing section by highlighting the recommended plan. Use subtle **skeuomorphic elements** for the payment cards and implement **collapsible sections** for the FAQ. Add **microinteractions** to the CTA buttons to increase their **affordance**.
```

This prompt combines conversion psychology with interaction design to improve a specific high-value interface section.