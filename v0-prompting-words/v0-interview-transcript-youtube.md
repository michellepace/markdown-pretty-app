# Prompting v0.dev

This is a cleaned and summarised version of the YouTube transcript from [Vercel's VP of Product on how to use v0 step-by-step to build your own ideas](https://youtu.be/sCFS_U7d9Do).

## Basic Approach and Creative Modes
I'll share my approach with v0. There are two different creative modes I use:
1. When I have a specific opinion/vision
2. When I don't know what I want and let AI generate ideas

## Starting with References
My first tip: starting with screenshots is super helpful. For example, I wanted to build something similar to Spotify but more information dense with a nicer UI.

## One-Shot vs. Iterative Approach
For simple projects: "Build a page where I can post a link, hit a button, and it'll send it to Slack." I didn't specify UI details - just described functionality and v0 generated a usable component in one shot.

For more complex projects like my music player: I started with a reference screenshot and went through multiple iterations (reached V12).

## Specific Prompting Examples
Early prompts focused on styling:
- "Make it have warmer grays"
- "Use a Sanda font from Google fonts with next font"
- "Make the UI have a tighter information density"

Layout refinements:
- "The time playing bar should be longer"
- "The search input should have an actual input in it"
- "Add more realistic fake data for the songs"
- "Less vertical spacing between the rows"
- "Each row should have the album art to the left of it"
- "Make the default value of the search input 'electric'"
- "The playlist name should be aligned with playlist"
- "Make the album image art smaller"

## Using Technical Terms (Tailwind)
When you know specific technical terms, use them: "Make it size four" instead of describing size generally.

## Refining Layouts
Specific layout instructions:
- "Let's put the artist names in a column versus under the title"
- "Use this as a placeholder image for all of the albums"
- "Use electronic music for all of the placeholder data"

## Adding Media
Adding images dramatically improves designs (typography and imagery are key elements of web design).

## Natural Language Instructions
Using conversational language works well:
- "That now playing bar is pretty wide, I would probably make that less"
- "Don't make sure that the lines don't break into two lines"
- "Make the width of the column smaller"

## Leveraging Technical Knowledge
Using specific CSS properties: "Please use tabular-nums" (makes numbers vertically aligned)

## Responsive Design
Simple request: "Make the table mobile responsive"
Problem-solving: "I can't see the table of songs because the image is so large, can you fix it?"

## Component Architecture
Advanced requests:
- "Let's break this out into components"
- "Let's start trying to add some logic to it"
- "Adjust the color scheme to be darker than the original but not full black"

## For Beginners (Interviewer Question)
Q: Is it required to learn about web design before using v0?

A: Pre-existing knowledge helps you work faster, but it's not required. AI assistants can guide you with the right questions to ask.

## Asking for Design Advice
Example prompt for beginners: "I'm a novice at web design. I don't know what I'm doing. What can I try to make things look a little better? Any common practices or patterns?"

## Design Fundamentals v0 Suggested
- Consistent color scheme (2-3 main colors)
- Tailwind provides a design system with a grid of colors
- White space, padding, and margins
- Readable fonts (sans-serif fonts for better readability)
- Aligned and organized layout
- Responsive design
- High-quality images (crucial for professional appearance)
- Typography choices (serif vs sans-serif fonts)