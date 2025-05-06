# Powerful Prompting Words for v0.dev

A collection of prompting words for applications built with **shadcn/ui**, styled and themed with **Tailwind CSS**. Useful if you lack the vocabulary of a designer, or the words a frontend developer adept in Tailwind and shadcn/ui has. Includes prompt examples.

**Note 1 — Work in progress.** Words in section "[Words from v0 Interview Transcript](#words-from-v0-interview-transcript)" work, the remaining still to be validated.

References:
- [https://v0.dev](https://v0.dev/)
- [https://ui.shadcn.com](https://ui.shadcn.com/)
- [https://tailwindcss.com](https://tailwindcss.com/)
- [Design Terms Explained](https://www.contrast.studio/design-terms-explained)

---

## Table of Contents
- [Words from v0 Interview Transcript](#words-from-v0-interview-transcript)
  - [Design Specification Terms](#design-specification-terms)
  - [Layout Instructions](#layout-instructions)
  - [Component Architecture Terms](#component-architecture-terms)
  - [Technical Specificity Terms](#technical-specificity-terms)
  - [Responsive Design Terms](#responsive-design-terms)
  - [Prompt Examples](#prompt-examples)
- [UIUX Designer Words](#uiux-designer-words)
  - [Visual Design Principles](#visual-design-principles)
  - [Accessibility & Usability](#accessibility--usability)
  - [Information & Interaction Design](#information--interaction-design)
  - [Cognitive UX Principles](#cognitive-ux-principles)
- [Tailwind Words](#tailwind-words)
  - [Core Tailwind Concepts](#core-tailwind-concepts)
  - [Layout & Responsiveness](#layout--responsiveness)
  - [Interactive States](#interactive-states)
- [Shadcn Words](#shadcn-words)
  - [Core Component Architecture](#core-component-architecture)
  - [Navigation & Command Interfaces](#navigation--command-interfaces)
  - [Content Organization Components](#content-organization-components)
  - [Interactive Overlay Components](#interactive-overlay-components)
  - [Advanced Selection Components](#advanced-selection-components)
- [More Prompt Examples](#more-prompt-examples)

⌘

## Words from v0 Interview Transcript

---

Collected from a YouTube interview with v0.dev's VP of Product whilst building a prototype out. The original interview https://youtu.be/sCFS_U7d9Do and [summarised transcripted](./v0-interview-transcript.md)

### Design Specification Terms
1. `Warmer grays` - Specifying colour temperature shows design awareness and produces more aesthetically pleasing results
1. `Tighter information density` - Communicates layout priorities without needing to specify exact pixel measurements
1. `Tabular-nums` - Technical CSS property knowledge that solves specific visualization problems (vertically aligned numbers)
1. `Less vertical spacing` - Direct instruction about spacing that improves readability
1. `Darker than original but not full black` - Nuanced colour instruction showing understanding of contrast principles

### Layout Instructions
1. `Column versus under` - Clear positional language that specifies exact layout relationships
1. `Aligned with` - Precise alignment language that enforces visual hierarchy
1. `Make the width smaller` - Simple dimensional instruction that affects overall composition

### Component Architecture Terms
1. `Break out into components` - Shows understanding of React architecture and modular design
1. `Add logic to it` - Transitions from static design to functional components

### Technical Specificity Terms
1. `Inter font from Google fonts with next font` - Extremely specific typography instruction with implementation method
1. `Size four` - Direct reference to Tailwind's sizing system
1. `Placeholder image/data` - Request for realistic mockup content

### Responsive Design Terms
1. `Mobile responsive` - Triggers responsive design patterns without needing to specify breakpoints
1. `Fix [specific mobile issue]` - Problem-solving approach to responsive design

### Prompt Examples

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

(Generated and still need validation):

### Visual Design Principles

`Visual hierarchy`: **Directs attention flow through deliberate sizing, contrast, and positioning.** Eg.2 Provides specific Tailwind classes (z-index values and shadow) that v0.dev can directly implement rather than an abstract request.
1. *Establish a clearer visual hierarchy with the pricing tiers*
2. *Make the pricing tier cards use a z-20 shadow for the recommended option and z-10 for others to establish clearer visual hierarchy*

`Content hierarchy`: **Information importance signalling.** Eg.2 provides exact typography classes for different content levels instead of vague hierarchy requests.

1. *Not in original artifact*
2. *Create clear content hierarchy with text-2xl font-semibold for primary headings, text-lg font-medium for subheadings, and text-sm text-gray-600 for supporting text*

`Negative space`: **Strategic whitespace that improves focus and readability.** Eg2 uses specific Tailwind padding units that v0.dev can immediately apply instead of the vague "increase" instruction.

1. *Increase negative space around card elements*
2. *Add p-6 negative space around cards and increase to p-8 for the featured card*

`Card elevation`: **Visual prominence through shadows and positioning.** Eg2 establishes a complete system of elevation using specific shadow utilities and transform classes

1. *Not in original artifact*
2. *Use three levels of card elevation: shadow-sm for inactive items, shadow-md for standard cards, and shadow-lg with a -translate-y-1 for featured elements*

`Gestalt principles`: **Visual perception laws for unified design.** Translates abstract design theory into concrete Tailwind spacing classes.

1. *Not in original artifact*
2. *Apply the Gestalt principle of proximity by grouping related actions within a space-y-1 container and separating sections with a my-6 divider*

`Skeuomorphism vs. flat design`: **Interface styling approach.** Eg.2 provides implementation-ready Tailwind classes rather than leaving interpretation to the AI.

1. *Add subtle skeuomorphic elements to the flat design*
2. *Add subtle skeuomorphic effects with shadow-md and a 1px border-slate-200 on cards while maintaining the overall flat design aesthetic*

### Accessibility & Usability

`Accessibility contrast`: **WCAG compliance for text visibility.** Eg.2 provides exact color values and the required contrast ratio, giving v0.dev concrete parameters to work with.

1. *Ensure AAA accessibility contrast for all text elements*
2. *Use text-slate-900 on white backgrounds to ensure AAA accessibility contrast ratio of at least 7:1 for all body text*

`Affordance`: **Visual cues indicating interactivity.** Eg.2 includes specific Tailwind transition and shadow classes that create clear visual affordances.

1. *Make the button have stronger affordance*
2. *Increase button affordance with hover:scale-105 transition effects and an interactive shadow-sm hover:shadow-md*

`Interaction parity`: **Consistent behaviour across devices.** Eg.2 provides a specific class pairing that ensures consistent behaviour across different input methods.

1. *Not in original artifact*
2. *Ensure interaction parity by making hover:bg-slate-100 states have equivalent focus-visible:bg-slate-100 and active:bg-slate-200 states for keyboard/touch users*

### Information & Interaction Design

`Information architecture`: **Structured content organisation.** Eg.2 provides a specific grid system implementation.

1. *Improve the information architecture of the dashboard*
2. *Improve the dashboard's information architecture by using a grid-cols-12 layout with col-span-8 for primary content and col-span-4 for secondary information*

`Progressive disclosure`: **Revealing information gradually.** Eg.2 references a specific shadcn component and animation detail that v0.dev can implement directly.

1. *Use progressive disclosure for the complex settings*
2. *Implement progressive disclosure for advanced settings using a Disclosure component from shadcn with a chevron animation on toggle*

`Micro interactions`: **State-based animations providing feedback.** Eg.2 details exact animation classes, timing parameters, and a specific element to animate.

1. *Add micro interactions to form submissions*
2. *Add micro interactions using group-hover:translate-x-1 transition-all duration-200 to the chevron icon in the dropdown menu*

### Cognitive UX Principles

`Cognitive load`: **Mental effort required for interface use.** Eg.2 provides quantitative limits and specifies component choices. Eg.2 provides quantitative limits and specifies component choices.

1. *Reduce cognitive load in the checkout process*
2. *Reduce cognitive load in checkout by limiting form fields to max 4 per step and using shadcn/Form with built-in validation*

`Decision fatigue`: **Limited user decision capacity.** Eg.2 specifies styling approaches and numerical constraints that create immediately actionable instructions for v0.dev

- *Minimize decision fatigue in the onboarding flow*
- *Combat decision fatigue by using a bg-primary highlight for the recommended plan and limiting feature comparison to only 5 key differences*

## Tailwind Words

---

(Generated and still need validation):

### Core Tailwind Concepts

`Utility-first`: **Core Tailwind approach using single-purpose atomic classes instead of component classes.** Eg.2 demonstrates actual utility classes working together rather than just mentioning the concept abstractly.

1. *Create a utility-first navbar design*
2. *Create a utility-first navbar with flex justify-between items-center py-4 px-6 bg-white shadow-sm*

`JIT compiler`: **Just-in-time dynamic class generation that enables arbitrary values and variants.** Eg.2 shows specific arbitrary values that JIT enables rather than vague "animation effects."

1. *Leverage JIT compiler features for the animation effects*
2. *Leverage dynamic classes enabled by the JIT compiler like hover:translate-y-[2px] and bg-[#3b82f680]*

`Arbitrary values`: **Custom non-standard measurements using square bracket notation for precision.** Eg.2 demonstrates various formats of arbitrary values and how they can be used together.

1. *Use arbitrary values [w-42rem] for the hero section*
2. *Apply precise spacing with arbitrary values like pt-[72px] w-[37.5rem] and grid-cols-[1fr_2.5fr_1fr]*

`Custom colour palette`: **Extended theme colors beyond default Tailwind palette for brand consistency.** Eg.2 demonstrates how to reference custom color definitions rather than just using standard Tailwind colors.

1. *Use slate-800 for text and emerald-500 for accents*
2. *Apply our brand palette using custom colors text-brand-900 bg-brand-100 border-brand-300 where brand-900 is #0f172a*

### Layout & Responsiveness

`Responsive variants`: **Breakpoint-specific styling with sm:, md:, lg: and xl: prefixes.** Eg.2 provides complete responsive patterns across multiple breakpoints with specific class combinations.

1. *Use responsive variants for the sidebar: hidden on mobile, visible on md:*
2. *Use responsive variants: flex-col items-start gap-4 on mobile, sm:flex-row sm:items-center sm:gap-6 on tablet, and md:justify-between on desktop*

`Container queries`: **Component-specific responsive styling based on parent container width not viewport.** Eg.2 shows the exact syntax for container queries rather than just the concept.

1. *Implement container queries for the product cards*
2. *@container queries for a product card that's w-full @container(min-width: 300px):grid @container(min-width: 400px):grid-cols-2*

`Space-between`: **Flexbox distribution utility for spreading elements within a container.** Eg.2 provides a complete flexbox implementation pattern rather than a single property in isolation.

1. *Use space-between for the navigation items*
2. *Use flex justify-between items-center for the header with mr-auto on the logo and gap-4 between navigation items*

`Responsive typography`: **Screen-adaptive text sizing that changes at different breakpoints.** Eg.2 provides specific typography classes at different breakpoints rather than general responsive guidance.

1. *Not in original*
2. *Use text-xl lg:text-2xl xl:text-4xl font-bold for the hero heading and text-sm md:text-base text-gray-600 for the description*

`Spacing scale consistency`: **Harmonious proportional spacing using Tailwind's built-in spacing scale.** Eg.2 establishes a systematic approach to spacing with specific value relationships rather than arbitrary spacing.

1. *Not in original*
2. *Maintain spacing consistency using p-4 gap-2 for small components, p-6 gap-4 for medium components, and p-8 gap-6 for large components*

### Interactive States

`Dark mode`: **Light/dark theming using the dark: variant prefix for theme toggling.** Eg.2 includes transition effects and complete paired class sets for a seamless theme switch.

1. *Implement dark mode toggle with appropriate colour shifts*
2. *Implement dark mode with bg-white dark:bg-slate-900 text-slate-900 dark:text-white and transition-colors duration-200*

`Group-hover`: **Parent-trigger state changes using the group and group-hover: modifiers.** Eg.2 shows a complete parent-child relationship pattern with visibility controls rather than just mentioning effects.

1. *Apply group-hover effects to the card's action buttons*
2. *Create card with group hover effects: group hover:bg-slate-50 applied to the card and invisible group-hover:visible group-hover:opacity-100 on child buttons*

`Ring utilities`: **Focus state visualization using Tailwind's ring-width and ring-color utilities.** Eg.2 provides a complete accessible focus pattern with proper offsets rather than just mentioning rings generically.

1. *Add ring utilities for interactive elements*
2. *Add accessible focus states with ring-2 ring-offset-2 ring-blue-500 focus:outline-none focus-visible:ring on interactive elements*

`Multi-variant states`: **Combined interactive states using hover:, active:, focus: and disabled: prefixes.** Eg.2 demonstrates how to handle multiple state variants together rather than addressing each state separately.

1. *Not in original*
2. *Apply hover:bg-blue-600 active:bg-blue-700 focus:ring-2 disabled:opacity-50 disabled:bg-gray-300 disabled:cursor-not-allowed to the submit button*

`Pseudo-element styling`: **Using before: and after: variants to create decorative elements without extra markup.** Eg.2 provides complete pseudo-element styling pattern with positioning and gradient rather than basic decoration.

1. *Not in original*
2. *Add decorative elements with before:absolute before:top-0 before:left-0 before:w-full before:h-1 before:bg-gradient-to-r before:from-blue-500 before:to-purple-500*

## Shadcn Words

---

(Generated and still need validation):

### Core Component Architecture

`Radix primitives`: **Accessibility-first unstyled components that shadcn builds upon.** Eg.2 provides specific implementation details including accessibility attributes, interaction patterns, and sizing constraints.

1. *build upon Radix primitives for maximum compatibility*
2. *Implement a Select component using Radix primitives with proper aria-label attributes and keyboard navigation support with a max-h-[300px] scrollable dropdown*

`Compound components`: **Related component pieces that share state.** Eg.2 names all required subcomponents and explains their shared state management purpose.

1. *use compound components for the date picker*
2. *Create a Form compound component with FormField, FormItem, FormLabel, FormControl, FormDescription, and FormMessage subcomponents that handle validation state together*

`Polymorphic components`: **Components that can render as different HTML elements.** Eg.2 specifies the exact prop to use and provides a concrete use case scenario.

1. *make the button a polymorphic component*
2. *Make the Button component polymorphic using the asChild prop so it can wrap a NextLink component while maintaining all button styling*

### Navigation & Command Interfaces

`Command palette`: **Keyboard-accessible search interface.** Eg.2 details specific integration technology, filtering capabilities, and multiple activation methods.

1. *add a command palette for quick actions*
2. *Add a Command palette with cmdk integration that filters through page sections and supports both keyboard shortcuts (⌘K) and click activation*

`Drawer navigation`: **Side-sliding panel UI pattern.** Eg.2 specifies animation direction, backdrop styling, and state preservation behavior.

1. *add drawer navigation for mobile users*
2. *Create a Drawer navigation using shadcn that slides from the left on small screens with a backdrop blur-sm effect and preserves scroll position when closed*

`Sheet component`: **Side panel with various anchor positions.** Eg.2 details responsive sizing variations, positioning, and content purpose.

1. *add drawer navigation for mobile users*
2. *Create a Sheet component that slides in from the right side with size='sm' on mobile and 'default' on desktop, containing user notification preferences*

### Content Organization Components

`Accordion pattern`: **Expandable content sections.** Eg.2 specifies configuration props, behavior constraints, and animation customization details.

1. *organize content in an accordion pattern*
2. *Use an Accordion with collapsible={false} type='single' to ensure one section always remains open, and customize the ChevronDown icon animation duration to 150ms*

`Collapsible sections`: **Toggle visibility content areas.** Eg.2 details custom button creation and multiple visual state indicators.

1. *implement collapsible sections for the FAQ items*
2. *Build FAQ items using Collapsible components with a custom CollapseButton that includes both a plus/minus icon transition and text color change on expanded state*

`Tabs with content`: **Organized sectioned interface.** Eg.2 provides initialization details, quantifies content sections, specifies styling variant, and explains interaction behavior.

1. *organize content in an accordion pattern*
2. *Build a TabsList with defaultValue='overview' and three Tab panels using underlined variant that dynamically swaps content without page reload*

### Interactive Overlay Components

`Context menu`: **Right-click action interface.** Eg.2 specifies nested menu structure, icon integration, keyboard support, and text styling.

1. *implement a context menu for additional options*
2. *Implement a Context menu with submenus for file actions that includes icons from lucide-react and keyboard shortcuts displayed right-aligned in text-muted-foreground*

`Dialogue modals`: **Focus-trapping overlay components.** Eg.2 details a multi-step implementation with specific typography styling and action button requirements.

1. *use a dialogue modal for the confirmation step*
2. *Use a Dialogue modal with a 3-step onboarding flow that uses Dialogue.Title with text-2xl and Dialogue.Description with text-muted, ensuring each step has a clear primary action button*

`Toast notifications`: **Temporary feedback messages.** Eg.2 specifies the hook implementation, multiple variants for different states, timing configuration, and positioning.

1. *show toast notifications for form submissions*
2. *Show Toast notifications using useToast() hook with variant='destructive' for errors and duration={3000} for success messages, positioned in the bottom-right corner*

`Hover Card`: **Rich preview popover for elements.** Eg.2 details timing configuration, visual styling, and specific implementation use case.

1. *show toast notifications for form submissions*
2. *Add HoverCard components to user avatars showing detailed profile info with a 300ms openDelay and a subtle shadow-md border rounded-xl*

### Advanced Selection Components

`Combobox with filtering`: **Searchable dropdown selection.** Eg.2 specifies dynamic filtering behavior, accessibility support, and custom content rendering capabilities.

1. *implement a context menu for additional options*
2. *Implement a Combobox component that filters countries as you type with support for keyboard navigation and custom rendering of flag icons next to each option*

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
