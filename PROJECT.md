# openemg.com frontend

We are building a webpage for openemg.com, a startup focusing on using emg devices for accessibility tech. We specialize in computer use devices.

### Who are customers are
- People with disabilities that make it harder to use a computer or other electronic device

## Compoments

- Navbar - simple navbar with home, contact (to interest form section of landing page), demos, tech
- Logo is openemg.png in static
- Landing page
    - Mission Statement (We are using EMGs devices to promote agency)
    - What is the technology (link to technology page)(link to demos)(EMG, EEG)
    - What we offer (contracting, you tell me what problems you have, we figure out a solution, I make it)
    - Interest form (Name, email, I agreed to receive email updates)
        - Footer for interest form - book a meeting (https://calendar.google.com/calendar/u/0/appointments/schedules/AcZssZ31U1ZeaAnwogXmoWvbnBHSB2HAX7HI5UH6qFAuOLnK_aWvDUA9B6b_G20DoPSqYuGFtHVL6FRL)
- Demos
    - EEG for computer use with eye and facial movement (https://www.youtube.com/watch?v=xK5VmC4PBDk&t=1s)
- Tech
    - Surface EMG
        - Use the emg_demo.jpg in static
        - Wikipedia (https://en.wikipedia.org/wiki/Electromyography)
        - Paper (https://pmc.ncbi.nlm.nih.gov/articles/PMC3821366/)

### Theme

--color-gunmetal-50: #f1f3f2;
--color-gunmetal-100: #e4e7e6;
--color-gunmetal-200: #c9cfcc;
--color-gunmetal-300: #aeb7b3;
--color-gunmetal-400: #939f99;
--color-gunmetal-500: #788780;
--color-gunmetal-600: #606c66;
--color-gunmetal-700: #48514d;
--color-gunmetal-800: #303633;
--color-gunmetal-900: #181b1a;
--color-gunmetal-950: #111312;

--color-aquamarine-50: #eafbf5;
--color-aquamarine-100: #d4f7ec;
--color-aquamarine-200: #aaeed9;
--color-aquamarine-300: #7fe6c5;
--color-aquamarine-400: #55ddb2;
--color-aquamarine-500: #2ad59f;
--color-aquamarine-600: #22aa7f;
--color-aquamarine-700: #19805f;
--color-aquamarine-800: #115540;
--color-aquamarine-900: #082b20;
--color-aquamarine-950: #061e16;

--color-lavender-blush-50: #f5f0f2;
--color-lavender-blush-100: #ebe0e5;
--color-lavender-blush-200: #d7c1cb;
--color-lavender-blush-300: #c3a2b1;
--color-lavender-blush-400: #ae8497;
--color-lavender-blush-500: #9a657d;
--color-lavender-blush-600: #7b5164;
--color-lavender-blush-700: #5d3c4b;
--color-lavender-blush-800: #3e2832;
--color-lavender-blush-900: #1f1419;
--color-lavender-blush-950: #160e11;

--color-fiery-terracotta-50: #fdece7;
--color-fiery-terracotta-100: #fcd8cf;
--color-fiery-terracotta-200: #f9b19f;
--color-fiery-terracotta-300: #f68a6f;
--color-fiery-terracotta-400: #f3633f;
--color-fiery-terracotta-500: #f03c0f;
--color-fiery-terracotta-600: #c0300c;
--color-fiery-terracotta-700: #902409;
--color-fiery-terracotta-800: #601806;
--color-fiery-terracotta-900: #300c03;
--color-fiery-terracotta-950: #220802;

--color-vivid-orchid-50: #f8ecf8;
--color-vivid-orchid-100: #f2d9f1;
--color-vivid-orchid-200: #e4b4e3;
--color-vivid-orchid-300: #d78ed5;
--color-vivid-orchid-400: #ca68c7;
--color-vivid-orchid-500: #bd42b9;
--color-vivid-orchid-600: #973594;
--color-vivid-orchid-700: #71286f;
--color-vivid-orchid-800: #4b1b4a;
--color-vivid-orchid-900: #260d25;
--color-vivid-orchid-950: #1a091a;

Use this repo for ui inspiration https://github.com/olegpolin/neobrutalism-svelte

## Documentation

#### Svelte 5

MCP: ✅ Official MCP available — @sveltejs/mcp Provides live Svelte 5 docs, autofixing of anti-patterns, and Svelte-aware code analysis. Prevents the common failure mode of AI assistants defaulting to React/Vue patterns when writing Svelte code.

"svelte": {
  "command": "npx",
  "args": ["-y", "@sveltejs/mcp"]
}
Docs: https://svelte.dev/docs

#### Tailwind CSS 4

MCP: ❌ No official MCP. Use docs directly. Docs: https://tailwindcss.com/docs

#### Neobrutalism Design System

MCP: ❌ No official MCP. Reference the GitHub repo directly. Reference: https://github.com/olegpolin/neobrutalism-svelte