# Media Queries vs Container Queries

This page demonstrates the difference between Media Queries and Container Queries. It was built with Svelte and hosted on Vercel.

## Page Content

The page contains two containers:

1. **Media Queries Container**: This container changes its layout based on the width of the viewport.
2. **Container Queries Container**: This container changes its layout based on the width of the container.

A slider allows the user to change the width of the container and observe the differences between the two approaches.

### Differences between Media Queries and Container Queries

- **Media Queries**:
  - Change the layout based on the width of the viewport.
  - Useful for global layout changes.

- **Container Queries**:
  - Change the layout based on the width of the container.
  - Useful for components that need to adapt dynamically.

## Building the Page

### Svelte

The page was built using the Svelte framework. Svelte is a modern JavaScript framework for building reactive user interfaces.

### Vercel

The page is hosted on Vercel. Vercel is a platform for hosting static sites and serverless functions.

## Code Structure

### `+page.svelte`

This is the main file of the page. It contains the HTML, CSS, and JavaScript code that defines the page.

#### HTML

The HTML part of the file contains the structure of the page, including the two containers and the slider.

#### CSS

The CSS part of the file contains the styles for the page, including the Media Queries and Container Queries.

#### JavaScript

The JavaScript part of the file contains the logic for the slider that changes the width of the container.
