# Fallback content inside video tag not displayed

This repository demonstrates an uncommon HTML bug where the fallback content inside the `<video>` tag is not displayed correctly.

## Bug Description

The bug occurs when a paragraph element (`<p>`) is placed inside the `<video>` element as fallback content.  While the `<video>` element supports fallback content for browsers that don't support the specified video formats, placing block-level elements like `<p>` directly inside `<video>` is not valid HTML5.

If a browser doesn't support the provided video formats, it will not render the paragraph element within the `<video>` tag, and the fallback message won't be displayed as intended. The correct approach is to place text content directly within the `<video>` tag or to correctly place the fallback content after the source tags

## Reproduction Steps

1. Open the `bug.html` file in a web browser that does not fully support HTML5 video or has disabled support.
2. Observe that the expected fallback message within the `<p>` tag is not displayed.

## Solution

The `bugSolution.html` file demonstrates the correct way to handle fallback content within the `<video>` element. The solution involves placing fallback text content directly within the `<video>` tag after the source elements, ensuring it is rendered correctly by browsers that do not support the specified video formats.

## Example

**bug.html (Incorrect):**
```html
<video>
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video.</p>
</video>
```

**bugSolution.html (Correct):**
```html
<video>
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  Your browser doesn't support HTML5 video.
</video>
```