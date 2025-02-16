# Bouncing Bell Partitions

This repository contains a **Bell number visualization** website that illustrates set partitions using **bouncing pastel-colored circles**. The project also includes a **dark theme toggle** for easy readability in different lighting conditions. It is built with **Jekyll** front matter, so you can run it locally or host it on GitHub Pages (or another static site host).

## Features

- **Bell Number Calculation**  
  For an integer $n$, the site enumerates all possible set partitions of $1, 2, \ldots, n$. The number of partitions (the Bell number) is displayed at the top.

- **Bouncing Pastel Circles**  
  Each partition is displayed in its own circle, which **bounces** around the screen in a simple animation loop. The circle color is chosen from a **random pastel** palette, with text automatically set to black or white for contrast.

- **Dark Theme Toggle**  
  A button allows switching between **light** mode and **dark** mode, changing background, text, link, and border colors for more comfortable viewing.

- **Mobile Optimization**  
  The layout includes a **responsive** design so that it scales down for smaller screens, shrinking circles and adjusting container height.

- **Jekyll Integration**  
  The file includes standard Jekyll front matter and references to `{% include analytics.html %}` and `{% seo %}`. You can easily run it as a Jekyll site or serve it via GitHub Pages.

## Getting Started

### 1. Cloning / Downloading the Repository

1. Clone the repository:

   ```bash
   git clone https://github.com/eric15342335/bells-number.git
   ```

2. Navigate to the project folder:

   ```bash
   cd <repo-name>
   ```

### 2. Running Locally with Jekyll

If you want to use the **Jekyll** features (like front matter and SEO tags):

1. Make sure you have Ruby and Bundler installed.
2. Install dependencies:

   ```bash
   bundle install
   ```

3. Serve the site locally:

   ```bash
   bundle exec jekyll serve
   ```

4. Open [http://127.0.0.1:4000](http://127.0.0.1:4000) in your browser to see the site.

### 3. Viewing Without Jekyll

If you **don’t** need Jekyll’s functionality (and just want the HTML/JS demo), you can simply open the generated `_site/index.html` (after building) **or** open the file directly in a browser. However, note that Jekyll templating and includes won’t be processed in that scenario, so some references might not work as intended.

## Usage

1. **Enter an integer** (≤ 7 recommended, due to exponential growth of partitions).
2. Click **Generate** to create all set partitions, which appear as bouncing circles.
3. The **Bell number** is displayed in the bar just below the controls.
4. Click **Toggle Dark Theme** to switch between light/dark modes.
5. Mobile devices or narrow screens will automatically reduce circle size to fit.

## Code Overview

- **Front Matter**  

  ```
  ---
  title: Bouncing Bell Partitions
  ---
  ```

  Used by Jekyll for the site title, includes, and SEO metadata.

- **HTML/JS**  
  A single file contains:
  - **CSS Variables & Themes** controlling light/dark colors.  
  - **JavaScript** for:  
    - Generating partitions (Bell number)  
    - Creating & animating the circles  
    - Dark theme toggling  
    - Random pastel color generation  
  - **Responsive** media queries to adjust bubble/container size on smaller screens.

- **Animation Loop**  
  Uses a `requestAnimationFrame` loop to continuously update each circle’s position and bounce them off the edges of the container.

## Customization

- **Colors**: Adjust color variables in the `:root` and `:root.dark` sections.
- **Bubbles**: Modify `.bubble` width/height or the random pastel generation in the JS to change appearance.
- **Dark Theme**: Tweak any variables under `:root.dark` to adjust background/text/link colors.
- **Performance**: If you allow large $n$, the number of partitions grows quickly, which can impact performance. Consider limiting $n$ or optimizing rendering.
