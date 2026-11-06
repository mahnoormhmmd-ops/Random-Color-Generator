# 🎨 Random Color Generator

> Generates a grid of 30 random colours with their hex codes, so you can find your next favourite shade.

A small web project built with plain HTML, CSS, and JavaScript. Every time the page loads, it creates 30 colour boxes, gives each a random hex colour, and shows the code on top of it.

**Live demo:** 
https://random-color-generator-three-azure.vercel.app/

## Features

- 30 colour boxes generated dynamically with JavaScript (none are written in the HTML)
- A random 6-digit hex code for each box, displayed on the colour itself
- Responsive grid that wraps to fit any screen size
- Rounded boxes with a text shadow so the codes stay readable
- No frameworks or libraries, just open it and it works

## Built with

| Language | What I used it for |
|----------|--------------------|
| **HTML5** | Page structure: a heading and an empty container |
| **CSS3** | Flexbox with wrapping, centred text, rounded borders, text shadow |
| **JavaScript (vanilla)** | Creating elements, generating random hex codes, setting background colours |

## How I made this

- **Tutorial or not:** [Pick one and edit: "I built this on my own, using MDN and Google when I got stuck." / "I followed [tutorial name/link] for the main idea, then changed the design, fonts, and number of boxes myself."]
- **Tools:** [e.g. VS Code, Live Server, Git and GitHub]
- **Process:**
  1. Wrote the basic HTML with an empty container
  2. Styled the colour boxes with flexbox
  3. Used a loop in JavaScript to create 30 `div` elements
  4. Wrote a function that builds a random hex code
  5. Applied each code as the box's background colour and text
  6. Fixed bugs and uploaded to GitHub

## How it works

1. A `for` loop creates 30 `div` elements with the class `color-container` and adds them to the page.
2. `randomColor()` builds a 6-character string by picking a random character from `0123456789abcdef` six times.
3. `generateColors()` goes through every box, gets a new random code, and uses it as the box's background colour and its text.

```javascript
function randomColor() {
    const chars = "0123456789abcdef";
    let color = "";
    for (let index = 0; index < 6; index++) {
        const randomNum = Math.floor(Math.random() * chars.length);
        color += chars.charAt(randomNum);
    }
    return color;
}
```

## What I learned

- How to **create HTML elements with JavaScript** using `createElement` and `appendChild`
- How to use a **`for` loop** to repeat a task instead of copying code
- How **hex colour codes** work: 6 characters from 0-9 and a-f
- How `Math.random()` and `Math.floor()` work together to pick random items
- How `querySelectorAll` and `forEach` let you change many elements at once
- That the **order of code matters**: a variable can't be used before it is created

## What I struggled with

- **Typos in variable names.** `colorConatinerEl` and `colorConatinerEls` looked almost the same but made the script crash. Careful naming (and checking the console with `F12`) helped.
- **Calling a function too early.** I called `generateColors()` before selecting the elements it needed.
- **Returning the wrong variable.** My function built `color` but returned `colorCode`, which didn't exist.
- **Random decimals.** `Math.random()` gives decimals, so I needed `Math.floor()` to get a whole index.

## Getting started

1. Clone the repository:
   ```bash
   git clone https://github.com/mahnoormhmmd-ops/Random-Color-Generator.git
   ```
2. Open the folder:
   ```bash
   cd random-color-generator
   ```
3. Open `index.html` in your browser. Refresh the page to get new colours!

## Project structure

```
random-color-generator/
├── index.html     # Page structure
├── style.css      # Grid layout and box styling
├── script.js      # Colour generation logic
└── README.md
```

## Ideas for the future

- [ ] A "Generate new colours" button
- [ ] Click a colour to copy its hex code
- [ ] Automatically switch text between black and white for readability
- [ ] Let the user choose how many colours to generate
- [ ] Save favourite colours with `localStorage`

## Author

Made by **Mahnoor Muhammad**.

https://random-color-generator-three-azure.vercel.app/
