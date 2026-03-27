# Flashcards Craft Landing Page

This is the landing page for **Flashcards Craft**, the ultimate tool for generating professional Anki flashcards in seconds.

## How to Run Locally

Since this is a static website, you can run it using any simple web server. Here are the most common methods:

### 1. Using Python (Recommended for macOS/Linux)
If you have Python installed, run the following command in the project root:

```bash
python3 -m http.server 8000
```
Then open [http://localhost:8000](http://localhost:8000) in your browser.

### 2. Using Node.js (npx)
If you have Node.js installed, you can use `serve`:

```bash
npx serve .
```
Then open the local URL provided in the terminal (usually [http://localhost:3000](http://localhost:3000)).

### 3. Using VS Code (Live Server)
If you use VS Code, the easiest way is to install the **Live Server** extension:
1. Open the project in VS Code.
2. Click the **"Go Live"** button in the bottom right corner of the window.
3. The website will open automatically in your default browser.

## Project Structure
- `index.html`: The main landing page.
- `styles.css`: Custom CSS for the "Luminous Precision" design system.
- `assets/`: Images and icons.
- `design-system/`: Design tokens and color palettes.
